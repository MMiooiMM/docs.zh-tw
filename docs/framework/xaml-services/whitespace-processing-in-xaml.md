---
title: XAML 中的空白字元處理
ms.date: 03/30/2017
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], white-space processing
- white-space processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
ms.openlocfilehash: 930e8a0013dd601aaafcd81340b3b9b8b69f8fdd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458504"
---
# <a name="white-space-processing-in-xaml"></a>XAML 中的空白字元處理
XAML 的語言規則狀態，必須由 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 處理器執行處理顯著的空白字元。 本主題說明這些 XAML 語言規則， 它也記載了由 XAML 處理器的 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 實作為序列化的 XAML 寫入器所定義的其他空白字元處理。  
  
<a name="whitespace_definition"></a>   
## <a name="white-space-definition"></a>空白字元定義  
 與 [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]一致，[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中的空白字元包括空格、換行字元和索引標籤。這些會分別對應至 Unicode 值0020、000A 和0009。  
  
<a name="whitespace_normalization"></a>   
## <a name="white-space-normalization"></a>空白字元正規化  
 根據預設，當 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 處理器處理 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 檔案時，就會發生下列空白字元正規化：  
  
1. 東亞字元間的換行字元會遭到移除。 如需這個詞彙的定義，請參閱本主題稍後的＜東亞字元＞一節。  
  
2. 所有空白字元（空格、換行字元、索引標籤）都會轉換成空格。  
  
3. 所有連續的空格會被刪除並取代為一個空格。  
  
4. 緊接在開始標記之後的空格會遭到刪除。  
  
5. 緊接在結束標記之前的空格會遭到刪除。  
  
 「預設」會對應到 [xml:space](xml-space-handling-in-xaml.md) 屬性的預設值所表示的狀態。  
  
<a name="whitespace_in_inner_text_and_string_primitives"></a>   
## <a name="white-space-in-inner-text-and-string-primitives"></a>內部文字中的空白字元和字串基本類型  
 上述正規化規則適用於 XAML 項目中的內部文字。 正規化後，XAML 處理器會依據下列情況將任何內部文字轉換成適當的類型：  
  
- 如果屬性的類型不是集合，但不是直接的 <xref:System.Object> 類型，XAML 處理器會嘗試使用該類型的類型轉換器，轉換成該類型。 在這裡轉換失敗會導致編譯時期錯誤。  
  
- 如果屬性的類型是集合，而且內部文字是連續的 (未插入項目標記)，內部文字會剖析為單一 <xref:System.String>。 如果集合類型無法接受 <xref:System.String>，這也會導致編譯時期錯誤。  
  
- 如果屬性的類型是 <xref:System.Object>，內部文字會剖析為單一 <xref:System.String>。 如果在其中插入項目標記，由於 <xref:System.Object> 類型即表示單一物件 (否則會是<xref:System.String> )，因此會導致編譯時期錯誤。  
  
- 如果屬性的類型是集合，而且內部文字不是連續的，第一個子字串會轉換成 <xref:System.String> 並加入做為集合項目，插入的項目也會加入做為集合項目，而最後的結尾子字串 (如果有的話) 會加入做為集合的第三個 <xref:System.String> 項目。  
  
<a name="preserving_whitespace"></a>   
## <a name="preserving-white-space"></a>保留空白字元  
 有數種技巧可保留來源 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中的泛空白字元，以進行最終簡報，而不會受到 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 處理器泛空白字元正規化的影響。  
  
 **xml： space = "preserve"** ：在專案層級指定此屬性，這是想要保留的空白字元。 這樣做會保留所有空白字元，其中包括程式碼編輯應用程式為了以視覺上直覺的巢狀結構來「美化」對齊項目可能加入的空格。 不過，這些空格的呈現與否是由包含項目的內容模型所決定。 請避免在根層級指定 `xml:space="preserve"`，因為不論您如何設定屬性，大部分的物件模型都不會將空白字元視為重要。 全域設定 `xml:space` 可能會對某些實作中的 XAML 處理 (特別是序列化) 帶來效能影響。 較好的作法是，只在轉譯字串內空白字元的專案層級上設定屬性，或使用空白字元的重要集合。  
  
 **實體和不分行空格**： [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 支援將任何 Unicode 實體放在文字物件模型內。 您可以使用專用實體，例如非中斷空間（& \#160; 採用 UTF-8 編碼）。 您也可以使用支援不分行空格字元的 RTF 文字控制項。 如果您使用實體來模擬縮排等版面配置特性，應該要特別小心，因為相較於在一般版面配置系統中產生縮排結果的功能 (例如適當使用面板和邊界)，實體的執行階段輸出會隨更多因素而改變。 例如，實體會回應使用者選取的字型，對應至相關字型並可能變更大小。  
  
<a name="east_asian_characters"></a>   
## <a name="east-asian-characters"></a>東亞字元  
 「東亞字元」定義為一組 Unicode 字元範圍 U + 20000 到 U + 2FFFD，以及 U + 30000 到 U + 3FFFD。 這個子集有時也稱為「CJK 表意字元」。 如需詳細資訊，請參閱<https://www.unicode.org>。  
  
<a name="whitespace_and_text_content_models"></a>   
## <a name="white-space-and-text-content-models"></a>空白字元和文字內容模型  
 在實務上，保留空白字元只是所有可能的內容模型子集的顧慮。 組成該子集的內容模型可以接受某種形式的單一 <xref:System.String> 類型、專用 <xref:System.String> 集合，或者 <xref:System.String> 和 <xref:System.Collections.IList> 或 <xref:System.Collections.Generic.ICollection%601> 集合中其他類型的混合。  
  
### <a name="white-space-and-text-content-models-in-wpf"></a>WPF 中的空白字元和文字內容模型  
 為了方便說明，本節的其餘部分將參考 WPF 所定義的特定類型。 本主題中所述的空白字元處理功能，通常都與 .NET Framework XAML 服務和 WPF 有關。 若要查看執行中的行為，您可以使用某個 WPF XAML 標記進行實驗，並在物件圖形中檢視結果，然後再重新序列化為標記。  
  
 即使是可以接受字串的內容模型，這些內容模型內的預設行為是，任何保留的空白字元都不會被視為重要的。 例如，<xref:System.Windows.Controls.ListBox> 會接受 <xref:System.Collections.IList>，但不會保留和呈現空白字元（例如，每個 <xref:System.Windows.Controls.ListBoxItem> 之間的分行符號）。 如果您嘗試使用換行字元做為 <xref:System.Windows.Controls.ListBoxItem> 項目之字串間的分隔符號，則完全無法運作；以換行字元分隔的字串會視為一個字串和一個項目。  
  
 將空白字元視為重要的集合通常是非固定格式檔模型的一部分。 支援空白字元保留行為的主要集合 <xref:System.Windows.Documents.InlineCollection>。 這個集合類別是使用 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>所宣告。找到這個屬性時，[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 處理器會將集合內的空白字元視為重要。 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> 表示的集合中，`xml:space="preserve"` 和空白字元的組合，就是保留並轉譯所有空白字元。 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> 中 `xml:space="default"` 和空白字元的組合，會導致先前所述的初始空白字元正規化，這會在特定位置留下一個空格，而這些空格會被保留和轉譯。 您可以自行決定要使用哪一種行為，而且您應該選擇性地使用 `xml:space` 來允許您想要的行為。  
  
 此外，在非固定格式檔模型中理貨單 linebreak 的某些內嵌專案，即使在空白字元的重要集合中也不會引進額外的空間。 例如，<xref:System.Windows.Documents.LineBreak> 元素的用途與 HTML 中的 \<BR/> 標記相同，因此在標記中的可讀性，通常會以撰寫的換行字元與任何後續文字區隔 <xref:System.Windows.Documents.LineBreak>。 該換行字元不應該正規化為下一行的前置空格。 若要啟用該行為，<xref:System.Windows.Documents.LineBreak> 專案的類別定義會套用 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>，然後由 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 處理器加以解讀，以表示一律會修剪 <xref:System.Windows.Documents.LineBreak> 周圍的空白字元。  
  
## <a name="see-also"></a>請參閱

- [XAML 概觀 (WPF)](../../desktop-wpf/fundamentals/xaml.md)
- [XML 字元實體和 XAML](xml-character-entities-and-xaml.md)
- [xml： XAML 中的空間處理](xml-space-handling-in-xaml.md)
