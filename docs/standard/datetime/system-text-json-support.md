---
title: System.Text.Json 中的 DateTime 和 DateTimeOffset 支援
description: 概述 system.string 程式庫中的 DateTime 和 DateTimeOffset 類型的支援方式。
ms.technology: dotnet-standard
author: layomia
ms.author: laakinri
ms.date: 07/22/2019
helpviewer_keywords:
- JSON, Serializer, Utf8
- JSON DateTime, JSON DateTimeOffset
- DateTime, DateTimeOffset
- JsonSerializer, Utf8JsonReader, Utf8JsonWriter, JsonElement, JsonDocument
- JSON Serializer, JSON Reader, JSON Writer
- Converter, JSON Converter, DateTime Converter
- ISO, ISO 8601, ISO 8601-1:2019
ms.openlocfilehash: 000a6b6dc892e65b50ae413ab3cb95d2a73ef0ef
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182583"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a>System.Text.Json 中的 DateTime 和 DateTimeOffset 支援

根據 ISO 8601:-2019 擴充設定檔，system.object 程式庫<xref:System.DateTime>會<xref:System.DateTimeOffset>剖析和寫入值。
[轉換器](xref:System.Text.Json.Serialization.JsonConverter%601)提供使用<xref:System.Text.Json.JsonSerializer>進行序列化和還原序列化的自訂支援。
使用<xref:System.Text.Json.Utf8JsonReader>和時， <xref:System.Text.Json.Utf8JsonWriter>也可以實作為自訂支援。

## <a name="support-for-the-iso-8601-12019-format"></a>支援 ISO 8601-1:2019 格式

<xref:System.Text.Json.JsonSerializer> <xref:System.DateTimeOffset> 、 <xref:System.DateTime> 、和類型<xref:System.Text.Json.JsonElement>會根據 ISO 8601-1:2019 格式的延伸設定檔來剖析和寫入和文字標記法，例如 2019-07-26T16 <xref:System.Text.Json.Utf8JsonWriter> <xref:System.Text.Json.Utf8JsonReader>：59:57-05:00。

<xref:System.DateTime>和<xref:System.DateTimeOffset>資料可以使用<xref:System.Text.Json.JsonSerializer>進行序列化：

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/csharp/serializing-with-jsonserializer/Program.cs)]

它們也可以使用<xref:System.Text.Json.JsonSerializer>還原序列化：

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-valid/Program.cs)]

使用預設選項時， <xref:System.DateTime>輸入<xref:System.DateTimeOffset>和文字標記法必須符合擴充 ISO 8601-1:2019 設定檔。
嘗試還原序列化不符合設定檔的標記法會導致<xref:System.Text.Json.JsonSerializer> <xref:System.Text.Json.JsonException>擲回：

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-error/Program.cs)]

提供 JSON 裝載內容的結構化存取，包括<xref:System.DateTime>和<xref:System.DateTimeOffset>標記法。 <xref:System.Text.Json.JsonDocument> 下列範例顯示如何在指定溫度的集合時，可以計算星期一的平均溫度：

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-valid/Program.cs)]

嘗試計算出具有不符合規範<xref:System.DateTime>之承載的平均溫度，會導致<xref:System.Text.Json.JsonDocument>擲<xref:System.FormatException>回：

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-error/Program.cs)]

較低層<xref:System.Text.Json.Utf8JsonWriter>級<xref:System.DateTime>的<xref:System.DateTimeOffset>寫入和資料：

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/writing-with-utf8jsonwriter/Program.cs)]

<xref:System.Text.Json.Utf8JsonReader>剖析<xref:System.DateTime> 和<xref:System.DateTimeOffset>資料：

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-valid/Program.cs)]

嘗試使用<xref:System.Text.Json.Utf8JsonReader>讀取不相容的格式會導致它<xref:System.FormatException>擲回：

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-error/Program.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset"></a>和的<xref:System.DateTime>自訂支援<xref:System.DateTimeOffset>

### <a name="when-using-xrefsystemtextjsonjsonserializer"></a>使用時<xref:System.Text.Json.JsonSerializer>

如果您想要序列化程式執行自訂剖析或格式設定，您可以實作為[自訂轉換器](xref:System.Text.Json.Serialization.JsonConverter%601)。
以下是一些範例：

#### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a>使用`DateTime(Offset).Parse`和`DateTime(Offset).ToString`

如果您無法判斷輸入<xref:System.DateTime>或<xref:System.DateTimeOffset>文字標記法的格式`DateTime(Offset).Parse` ，您可以在轉換子中使用方法讀取邏輯。 這可讓您使用。NET 對於剖析各種<xref:System.DateTime>和<xref:System.DateTimeOffset>文字格式的廣泛支援，包括非 iso 8601 字串和 ISO 8601 格式，但不符合延伸的 iso 8601-1:2019 設定檔。 相較于使用序列化程式的原生執行，此方法的效能大幅降低。

若要進行序列化，您可以`DateTime(Offset).ToString`在轉換器寫入邏輯中使用方法。 這可讓您使用<xref:System.DateTime>任何<xref:System.DateTimeOffset> [標準日期和時間格式](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)，以及[自訂日期和時間格式](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings)來撰寫和值。
相較于使用序列化程式的原生執行，這也會大幅降低效能。

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> 在執行<xref:System.Text.Json.Serialization.JsonConverter%601> `T`時，如果<xref:System.DateTime>是， `typeToConvert`則參數一律會`typeof(DateTime)`是。
參數適用于處理多型案例，以及使用泛型以高效能`typeof(T)`的方式取得時。

#### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a>使用<xref:System.Buffers.Text.Utf8Parser>和<xref:System.Buffers.Text.Utf8Formatter>

如果您的輸入<xref:System.DateTime>或<xref:System.DateTimeOffset>文字標記法符合其中一個 "R"、"l"、"O" 或 "G"[標準日期和時間格式字串](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)，或者您想要，您可以在轉換子邏輯中使用快速以 utf-8 為基礎的剖析和格式化方法。根據這些格式的其中一種來撰寫。 這比使用`DateTime(Offset).Parse`和`DateTime(Offset).ToString`更快。

這個範例會顯示根據<xref:System.DateTime> ["R" 標準格式](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier)序列化和還原序列化值的自訂轉換器：

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> "R" 標準格式的長度一律為29個字元。

#### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a>使用`DateTime(Offset).Parse`做為序列化程式的原生剖析

如果您通常會預期輸入<xref:System.DateTime>或<xref:System.DateTimeOffset>資料必須符合擴充 ISO 8601-1:2019 設定檔，您可以使用序列化程式的原生剖析邏輯。 您也可以只在案例中執行回溯機制。
這個範例顯示，在無法使用<xref:System.DateTime> <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>剖析文字標記法之後，轉換器會使用<xref:System.DateTime.Parse(System.String)>成功地剖析資料。

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example3/Program.cs)]

### <a name="when-writing-with-xrefsystemtextjsonutf8jsonwriter"></a>寫入時<xref:System.Text.Json.Utf8JsonWriter>

如果<xref:System.DateTime>您想要使用<xref:System.Text.Json.Utf8JsonWriter>撰寫自訂<xref:System.DateTimeOffset>或文字表示， <xref:System.String>您可以將自訂表格示格式格式化為`ReadOnlySpan<Byte>`、 `ReadOnlySpan<Char>`、或<xref:System.Text.Json.JsonEncodedText>，然後將它傳遞給對應的[Utf8JsonWriter. WriteStringValue](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestringvalue?view=netcore-3.0)或[Utf8JsonWriter. WriteString](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestring?view=netcore-3.0)方法。

下列範例顯示如何使用<xref:System.DateTime> <xref:System.DateTime.ToString(System.String,System.IFormatProvider)>來建立自訂格式<xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)> ，然後使用方法撰寫：

[!code-csharp[example-custom-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/custom-writing-with-utf8jsonwriter/Program.cs)]

### <a name="when-reading-with-xrefsystemtextjsonutf8jsonreader"></a>讀取時<xref:System.Text.Json.Utf8JsonReader>

如果您想要使用<xref:System.DateTime> <xref:System.Text.Json.Utf8JsonReader>讀取自訂<xref:System.DateTimeOffset>或文字表示，您可以<xref:System.String>使用<xref:System.Text.Json.Utf8JsonReader.GetString>來取得目前 JSON token 的值，然後使用自訂邏輯來剖析該值。

下列範例顯示如何使用<xref:System.DateTimeOffset> <xref:System.Text.Json.Utf8JsonReader.GetString>來抓取自訂文字表示，然後使用<xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)>進行剖析：

[!code-csharp[example-custom-reading-with-utf8jsonreader](~/samples/snippets/standard/datetime/json/csharp/custom-reading-with-utf8jsonreader/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a>在 system.string 中的延伸 ISO 8601-1:2019 設定檔

### <a name="date-and-time-components"></a>日期和時間元件

在中<xref:System.Text.Json>執行的延伸 ISO 8601-1:2019 設定檔會定義下列日期和時程表示的元件。 這些元件是用來定義剖析和格式化<xref:System.DateTime>和<xref:System.DateTimeOffset>標記法時，所支援的各種資料細微性層級。

| 元件       | 格式                      | 描述                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| Year            | "yyyy"                      | 0001-9999                                                                       |
| 月份           | "MM"                        | 01-12                                                                           |
| Day             | "dd"                        | 01-28、01-29、01-30、01-31 （以月/年為基礎）                                  |
| Hour            | "HH"                        | 00-23                                                                           |
| Minute          | "mm"                        | 00-59                                                                           |
| Second          | "ss"                        | 00-59                                                                           |
| 第二個分數 | "FFFFFFF"                   | 最少一個數位，最多16位數                                      |
| 時間位移     | "K"                         | "Z" 或 "（' + '/'-'） HH '： ' mm"                                                |
| 部分時間    | "HH '： ' mm '： ' ss [FFFFFFF]"     | 沒有 UTC 時差的時間資訊                                             |
| 完整日期       | "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-'dd"            | 行事曆日期                                                                   |
| 完整時間       | 「部分 time'K」           | 在當地時間與 UTC 之間時間位移的日或本地時間 UTC |
| 日期時間       | 「完整日期 ' 不是 '」完整時間 '」 | 行事曆日期和時間，例如 2019-07-26T16：59： 57-05：00                   |

### <a name="support-for-parsing"></a>支援剖析

下列資料細微性層級是針對剖析而定義：

1. 「完整日期」
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-'dd"

2. 「完整日期 ' 不是 ' ' 小時 ' '： ' ' 分鐘 '」
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM"

3. 「完整日期 ' 不是」 ' 部分時間 '」
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss" （可[排序（"s"）格式規範](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier)）
    2. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss '。 'FFFFFFF

4. 「完整日期 ' t ' ' 時間小時 ' '： ' ' 分鐘 ' ' 時間位移 '」
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' mmZ"
    2. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' mm （' + '/'-'） HH '： ' mm"

5. 「日期時間」
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ssZ"
    2. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss '。 'SS.FFFFFFFZ
    3. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss （' + '/'-'） HH '： ' MM"
    4. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss '。 'FFFFFFF （' + '/'-'） HH '： ' mm "

如果秒數有小數，則至少必須有一個數位。`2019-07-26T00:00:00.`不允許。
雖然允許最多16個小數位數，但只有前七個會經過剖析。 除了之外的任何專案都會被視為零。
例如， `2019-07-26T00:00:00.1234567890`將會剖析為`2019-07-26T00:00:00.1234567`。
這是為了與<xref:System.DateTime>實施保持相容，這僅限於此解決方案。

不支援閏秒。

### <a name="support-for-formatting"></a>支援格式化

下列資料細微性層級是針對格式而定義的：

1. 「完整日期 ' 不是」 ' 部分時間 '」
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss" （可[排序（"s"）格式規範](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier)）

        用來格式化不<xref:System.DateTime>含小數秒的，且不含位移資訊。

    2. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss '。 'FFFFFFF

        用來格式化<xref:System.DateTime> ，並以小數秒為單位，但不含位移資訊。

2. 「日期時間」
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ssZ"

        用來格式化<xref:System.DateTime>或<xref:System.DateTimeOffset>不含小數秒數，但使用 UTC 時差。

    2. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss '。 'SS.FFFFFFFZ

        用來格式化<xref:System.DateTime>或<xref:System.DateTimeOffset> （以毫秒為單位）和 UTC 時差。

    3. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss （' + '/'-'） HH '： ' MM"

        用來格式化<xref:System.DateTime>或<xref:System.DateTimeOffset>不含小數秒，但具有區域位移。

    4. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss '。 'FFFFFFF （' + '/'-'） HH '： ' mm "

        用來格式化<xref:System.DateTime>或<xref:System.DateTimeOffset> （以小數秒為單位），並使用本機位移。

如果存在，則會寫入最多7個小數位數。 這會與<xref:System.DateTime>實作為配合，僅限於此解析度。
