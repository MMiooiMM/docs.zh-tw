---
title: 使用可為 Null 的參考類型進行設計
description: 本進階教學課程提供可為 Null 的參考類型簡介。 您將了解如何在參考值可能為 Null 時表達您的設計意圖，以及在它們不能為 Null 時強制執行編譯器。
ms.date: 12/03/2018
ms.custom: mvc
ms.openlocfilehash: 7e4cb423658287e5260770a680f189c227b9cd01
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156686"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a><span data-ttu-id="ee891-104">教學課程：使用可為 Null 與不可為 Null 的參考類型更清楚地表達您的設計意圖</span><span class="sxs-lookup"><span data-stu-id="ee891-104">Tutorial: Express your design intent more clearly with nullable and non-nullable reference types</span></span>

<span data-ttu-id="ee891-105">C# 8 引進了**可為 Null 的參考類型**，其可利用可為 Null 的實值類型補充實值類型的相同方式來補充參考類型。</span><span class="sxs-lookup"><span data-stu-id="ee891-105">C# 8 introduces **nullable reference types**, which complement reference types the same way nullable value types complement value types.</span></span> <span data-ttu-id="ee891-106">您可以藉由將 `?` 附加至類型，來將變數宣告為**可為 Null 的參考類型**。</span><span class="sxs-lookup"><span data-stu-id="ee891-106">You declare a variable to be a **nullable reference type** by appending a `?` to the type.</span></span> <span data-ttu-id="ee891-107">例如，`string?` 代表可為 Null 的 `string`。</span><span class="sxs-lookup"><span data-stu-id="ee891-107">For example, `string?` represents a nullable `string`.</span></span> <span data-ttu-id="ee891-108">您可以使用這些新類型更清楚地表達設計意圖：部分變數「永遠都必須有值」，而其他變數「可能會遺漏值」。</span><span class="sxs-lookup"><span data-stu-id="ee891-108">You can use these new types to more clearly express your design intent: some variables *must always have a value*, others *may be missing a value*.</span></span>

<span data-ttu-id="ee891-109">在本教學課程中，您將了解如何：</span><span class="sxs-lookup"><span data-stu-id="ee891-109">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="ee891-110">在設計中併入可為 Null 與不可為 Null 的參考類型</span><span class="sxs-lookup"><span data-stu-id="ee891-110">Incorporate nullable and non-nullable reference types into your designs</span></span>
> * <span data-ttu-id="ee891-111">在整個程式碼中啟用可為 Null 的參考類型檢查。</span><span class="sxs-lookup"><span data-stu-id="ee891-111">Enable nullable reference type checks throughout your code.</span></span>
> * <span data-ttu-id="ee891-112">撰寫程式碼，以使編譯器強制執行這些設計決策。</span><span class="sxs-lookup"><span data-stu-id="ee891-112">Write code where the compiler enforces those design decisions.</span></span>
> * <span data-ttu-id="ee891-113">在您自己的設計中使用可為 Null 的參考功能</span><span class="sxs-lookup"><span data-stu-id="ee891-113">Use the nullable reference feature in your own designs</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ee891-114">必要條件</span><span class="sxs-lookup"><span data-stu-id="ee891-114">Prerequisites</span></span>

<span data-ttu-id="ee891-115">您將必須設定電腦來執行 .NET Core，包括 C# 8.0 搶鮮版 (Beta) 編譯器。</span><span class="sxs-lookup"><span data-stu-id="ee891-115">You’ll need to set up your machine to run .NET Core, including the C# 8.0 beta compiler.</span></span> <span data-ttu-id="ee891-116">C# 8 搶鮮版 (Beta) 編譯器隨附於 [Visual Studio 2019 Preview 1](https://visualstudio.microsoft.com/vs/preview/) \(英文\) 或 [.NET Core 3.0 Preview 1](https://dotnet.microsoft.com/download/dotnet-core/3.0) \(英文\)。</span><span class="sxs-lookup"><span data-stu-id="ee891-116">The C# 8 beta compiler is available with [Visual Studio 2019 preview 1](https://visualstudio.microsoft.com/vs/preview/), or [.NET Core 3.0 preview 1](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="ee891-117">本教學課程假設您已熟悉 C# 和 .NET，包括 Visual Studio 或 .NET Core CLI。</span><span class="sxs-lookup"><span data-stu-id="ee891-117">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="incorporate-nullable-reference-types-into-your-designs"></a><span data-ttu-id="ee891-118">在設計中併入可為 Null 的參考類型</span><span class="sxs-lookup"><span data-stu-id="ee891-118">Incorporate nullable reference types into your designs</span></span>

<span data-ttu-id="ee891-119">在本教學課程中，您會建置程式庫來將問卷執行模型化。</span><span class="sxs-lookup"><span data-stu-id="ee891-119">In this tutorial, you'll build a library that models running a survey.</span></span> <span data-ttu-id="ee891-120">程式碼會使用可為 Null 的參考類型和不可為 Null 的參考類型來代表真實世界的概念。</span><span class="sxs-lookup"><span data-stu-id="ee891-120">The code uses both nullable reference types and non-nullable reference types to represent the real-world concepts.</span></span> <span data-ttu-id="ee891-121">問卷問題絕對不能是 Null。</span><span class="sxs-lookup"><span data-stu-id="ee891-121">The survey questions can never be null.</span></span> <span data-ttu-id="ee891-122">受訪者可能不想回答問題。</span><span class="sxs-lookup"><span data-stu-id="ee891-122">A respondent might prefer not to answer a question.</span></span> <span data-ttu-id="ee891-123">在此情況下，回應可能是 Null。</span><span class="sxs-lookup"><span data-stu-id="ee891-123">The responses might be null in this case.</span></span>

<span data-ttu-id="ee891-124">您將為此範例撰寫的程式碼會表達該意圖，而編譯器會強制執行該意圖。</span><span class="sxs-lookup"><span data-stu-id="ee891-124">The code you'll write for this sample expresses that intent, and the compiler enforces that intent.</span></span>

## <a name="create-the-application-and-enable-nullable-reference-types"></a><span data-ttu-id="ee891-125">建立應用程式並啟用可為 Null 的參考類型</span><span class="sxs-lookup"><span data-stu-id="ee891-125">Create the application and enable nullable reference types</span></span>

<span data-ttu-id="ee891-126">在 Visual Studio 中或從命令列中使用 `dotnet new console` 來建立新的主控台應用程式。</span><span class="sxs-lookup"><span data-stu-id="ee891-126">Create a new console application either in Visual Studio or from the command line using `dotnet new console`.</span></span> <span data-ttu-id="ee891-127">為應用程式 `NullableIntroduction` 命名。</span><span class="sxs-lookup"><span data-stu-id="ee891-127">Name the application `NullableIntroduction`.</span></span> <span data-ttu-id="ee891-128">一旦建立應用程式之後，您將必須啟用 C# 8 搶鮮版 (Beta) 功能。</span><span class="sxs-lookup"><span data-stu-id="ee891-128">Once you've created the application, you'll need to enable C# 8 beta features.</span></span> <span data-ttu-id="ee891-129">開啟 `csproj` 檔案，並將 `LangVersion` 元素新增到 `PropertyGroup` 元素：</span><span class="sxs-lookup"><span data-stu-id="ee891-129">Open the `csproj` file, and add a `LangVersion` element to the `PropertyGroup` element:</span></span>

```xml
<LangVersion>8.0</LangVersion>
```

<span data-ttu-id="ee891-130">或者，您可以使用 Visual Studio 專案屬性來啟用 C# 8。</span><span class="sxs-lookup"><span data-stu-id="ee891-130">Alternatively, you can use the Visual Studio project properties to enable C# 8.</span></span> <span data-ttu-id="ee891-131">在 [方案總管] 中，以滑鼠右鍵按一下專案節點，然後選取 [屬性]。</span><span class="sxs-lookup"><span data-stu-id="ee891-131">In Solution Explorer, right click on the project node, select **Properties**.</span></span> <span data-ttu-id="ee891-132">接著，選取 [建置] 索引標籤，然後按一下 [進階...]。在語言版本的下拉式清單中，選取 [C# 8.0 搶鮮版 (Beta)]。</span><span class="sxs-lookup"><span data-stu-id="ee891-132">Then, select the **build** tab, and click **Advanced...**. In the dropdown for language version, select **C# 8.0 (beta)**.</span></span>

<span data-ttu-id="ee891-133">您必須選擇參與**可為 Null 的參考類型**功能，甚至是在 C# 8 專案中。</span><span class="sxs-lookup"><span data-stu-id="ee891-133">You must opt into the **nullable reference types** feature, even in C# 8 projects.</span></span> <span data-ttu-id="ee891-134">這是因為一旦開啟此功能之後，現有的參考變數宣告就會變成**不可為 Null 的參考類型**。</span><span class="sxs-lookup"><span data-stu-id="ee891-134">That's because once the feature is turned on, existing reference variable declarations become **non-nullable reference types**.</span></span> <span data-ttu-id="ee891-135">儘管該決策將可協助您找出現有程式碼可能不具適當 Null 檢查的問題，但它可能不會正確地反映您的原始設計意圖。</span><span class="sxs-lookup"><span data-stu-id="ee891-135">While that decision will help find issues where existing code may not have proper null-checks, it may not accurately reflect your original design intent.</span></span> <span data-ttu-id="ee891-136">您要使用新的 pragma 來開啟此功能：</span><span class="sxs-lookup"><span data-stu-id="ee891-136">You turn on the feature with a new pragma:</span></span>

```csharp
#nullable enable
```

<span data-ttu-id="ee891-137">您可以在原始程式檔中的任一處新增上述 pragma，並從該點開啟可為 Null 的參考類型功能。</span><span class="sxs-lookup"><span data-stu-id="ee891-137">You can add the preceding pragma anywhere in a source file, and the nullable reference type feature is turned on from that point.</span></span> <span data-ttu-id="ee891-138">此 pragma 也支援使用 `disable` 引數來關閉該功能。</span><span class="sxs-lookup"><span data-stu-id="ee891-138">The pragma also supports the `disable` argument to turn off the feature.</span></span>

<span data-ttu-id="ee891-139">您也可以藉由將下列元素新增到 .csproj 檔案，為整個專案開啟**可為 Null 的參考類型**，例如，緊接在啟用 C# 8.0 的 `LangVersion` 元素後面：</span><span class="sxs-lookup"><span data-stu-id="ee891-139">You can also turn on **nullable reference types** for an entire project by adding the following element to your .csproj file, for example, immediately following the `LangVersion` element that enabled C# 8.0:</span></span>

```xml
<NullableReferenceTypes>true</NullableReferenceTypes>
```

### <a name="design-the-types-for-the-application"></a><span data-ttu-id="ee891-140">設計適用於應用程式的類型</span><span class="sxs-lookup"><span data-stu-id="ee891-140">Design the types for the application</span></span>

<span data-ttu-id="ee891-141">此問卷應用程式需要建立一些類別：</span><span class="sxs-lookup"><span data-stu-id="ee891-141">This survey application requires creating a number of classes:</span></span>

- <span data-ttu-id="ee891-142">用來將問題清單模型化的類別。</span><span class="sxs-lookup"><span data-stu-id="ee891-142">A class that models the list of questions.</span></span>
- <span data-ttu-id="ee891-143">用來將已針對問卷連絡之人員清單模型化的類別。</span><span class="sxs-lookup"><span data-stu-id="ee891-143">A class that models a list of people contacted for the survey.</span></span>
- <span data-ttu-id="ee891-144">用來將填寫問卷的人員所提供的答案模型化的類別。</span><span class="sxs-lookup"><span data-stu-id="ee891-144">A class that models the answers from a person that took the survey.</span></span>

<span data-ttu-id="ee891-145">這些類型將使用可為 Null 和不可為 Null 的參考類型，來表達哪些成員是必要的，而哪些成員是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="ee891-145">These types will make use of both nullable and non-nullable reference types to express which members are required and which members are optional.</span></span> <span data-ttu-id="ee891-146">可為 Null 的參考類型會清楚地傳達該設計意圖：</span><span class="sxs-lookup"><span data-stu-id="ee891-146">Nullable reference types communicate that design intent clearly:</span></span>

- <span data-ttu-id="ee891-147">屬於問卷一部分的問題絕對不能是 Null：詢問空白的問題並無任何意義。</span><span class="sxs-lookup"><span data-stu-id="ee891-147">The questions that are part of the survey can never be null: It makes no sense to ask an empty question.</span></span>
- <span data-ttu-id="ee891-148">受訪者絕對不能是 Null。</span><span class="sxs-lookup"><span data-stu-id="ee891-148">The respondents can never be null.</span></span> <span data-ttu-id="ee891-149">您會想要追蹤連絡過的人員，甚至是拒絕參與的受訪者。</span><span class="sxs-lookup"><span data-stu-id="ee891-149">You'll want to track people you contacted, even respondents that declined to participate.</span></span>
- <span data-ttu-id="ee891-150">對於問題的任何回應可能會是 Null。</span><span class="sxs-lookup"><span data-stu-id="ee891-150">Any response to a question may be null.</span></span> <span data-ttu-id="ee891-151">受訪者可以拒絕回答部分或所有問題。</span><span class="sxs-lookup"><span data-stu-id="ee891-151">Respondents can decline to answer some or all questions.</span></span>

<span data-ttu-id="ee891-152">如果您使用了 C# 進行程式設計，則可能已經習慣允許 Null 值的參考類型，而您可能錯過了其他機會來宣告不可為 Null 的執行個體：</span><span class="sxs-lookup"><span data-stu-id="ee891-152">If you've programmed in C#, you may be so accustomed to reference types that allow null values that you may have missed other opportunities to declare non-nullable instances:</span></span>

- <span data-ttu-id="ee891-153">問題的集合不應為 Null。</span><span class="sxs-lookup"><span data-stu-id="ee891-153">The collection of questions should be non-nullable.</span></span>
- <span data-ttu-id="ee891-154">受訪者的集合不應為 Null。</span><span class="sxs-lookup"><span data-stu-id="ee891-154">The collection of respondents should be non-nullable.</span></span>

<span data-ttu-id="ee891-155">當您撰寫程式碼時，您會看到將不可為 Null 的參考類型作為參考的預設值，可避免可能導致 Null 參考例外狀況的常見錯誤。</span><span class="sxs-lookup"><span data-stu-id="ee891-155">As you write the code, you'll see that a non-nullable reference type as the default for references avoids common mistakes that could lead to null reference exceptions.</span></span> <span data-ttu-id="ee891-156">本教學課程的單元之一是您做了哪些變數可以或不可以是 Null 的決策。</span><span class="sxs-lookup"><span data-stu-id="ee891-156">One lesson from this tutorial is that you made decisions about which variables could or could not be null.</span></span> <span data-ttu-id="ee891-157">此語言不提供語法來表達那些決策。</span><span class="sxs-lookup"><span data-stu-id="ee891-157">The language didn't provide syntax to express those decisions.</span></span> <span data-ttu-id="ee891-158">但現在已提供。</span><span class="sxs-lookup"><span data-stu-id="ee891-158">Now it does.</span></span>

<span data-ttu-id="ee891-159">您要建置的應用程式將會執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ee891-159">The app you'll build will do the following steps:</span></span>

1. <span data-ttu-id="ee891-160">建立問卷並在其中新增問題。</span><span class="sxs-lookup"><span data-stu-id="ee891-160">Create a survey and add questions to it.</span></span>
1. <span data-ttu-id="ee891-161">為問卷建立一組虛擬隨機的受訪者。</span><span class="sxs-lookup"><span data-stu-id="ee891-161">Create a pseudo-random set of respondents for the survey.</span></span>
1. <span data-ttu-id="ee891-162">連絡受訪者，直到已完成的問卷大小達到目標數目為止。</span><span class="sxs-lookup"><span data-stu-id="ee891-162">Contact respondents until the completed survey size reaches the goal number.</span></span>
1. <span data-ttu-id="ee891-163">寫出有關問卷回應的重要統計資料。</span><span class="sxs-lookup"><span data-stu-id="ee891-163">Write out important statistics on the survey responses.</span></span>

## <a name="build-the-survey-with-nullable-and-non-nullable-types"></a><span data-ttu-id="ee891-164">使用可為 Null 與不可為 Null 的類型建置問卷</span><span class="sxs-lookup"><span data-stu-id="ee891-164">Build the survey with nullable and non-nullable types</span></span>

<span data-ttu-id="ee891-165">您將撰寫的第一個程式碼會建立問卷。</span><span class="sxs-lookup"><span data-stu-id="ee891-165">The first code you'll write creates the survey.</span></span> <span data-ttu-id="ee891-166">您會撰寫類別來將問卷問題和問卷執行模型化。</span><span class="sxs-lookup"><span data-stu-id="ee891-166">You'll write classes to model a survey question and a survey run.</span></span> <span data-ttu-id="ee891-167">您的問卷具有三種類型的問題，其會依答案的格式來區別：是/否的答案、數字答案，以及文字答案。</span><span class="sxs-lookup"><span data-stu-id="ee891-167">Your survey has three types of questions, distinguished by the format of the answer: Yes/No answers, number answers, and text answers.</span></span> <span data-ttu-id="ee891-168">建立 `public` `SurveyQuestion` 類別。</span><span class="sxs-lookup"><span data-stu-id="ee891-168">Create a `public` `SurveyQuestion` class.</span></span> <span data-ttu-id="ee891-169">緊接在 `using` 陳述式後面包含 `#nullable enable` pragma：</span><span class="sxs-lookup"><span data-stu-id="ee891-169">Include the `#nullable enable` pragma immediately after the `using` statements:</span></span>

```csharp
#nullable enable
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

<span data-ttu-id="ee891-170">新增 `#nullable enable` pragma，表示編譯器會將每個參考類型變數宣告解譯為**不可為 Null 的**參考類型。</span><span class="sxs-lookup"><span data-stu-id="ee891-170">Adding the `#nullable enable` pragma means the compiler interprets every reference type variable declaration as a **non-nullable** reference type.</span></span> <span data-ttu-id="ee891-171">您可以藉由新增問題文字的屬性和問題的類型來查看第一個警告，如下列程式碼所示：</span><span class="sxs-lookup"><span data-stu-id="ee891-171">You can see your first warning by adding properties for the question text and the type of question, as shown in the following code:</span></span>

```csharp
#nullable enable
namespace NullableIntroduction
{
    public enum QuestionType
    {
        YesNo,
        Number,
        Text
    }

    public class SurveyQuestion
    {
        public string QuestionText { get; }
        public QuestionType TypeOfQuestion { get; }
    }
}
```

<span data-ttu-id="ee891-172">由於您尚未將 `QuestionText` 初始化，因此，編譯器會發出警告，表示尚未將不可為 Null 的屬性初始化。</span><span class="sxs-lookup"><span data-stu-id="ee891-172">Because you haven't initialized `QuestionText`, the compiler issues a warning that a non-nullable property hasn't been initialized.</span></span> <span data-ttu-id="ee891-173">您的設計要求問題文字不可為 Null，因此，您也會新增建構函式來將它和 `QuestionType` 值初始化。</span><span class="sxs-lookup"><span data-stu-id="ee891-173">Your design requires the question text to be non-null, so you add a constructor to initialize it and the `QuestionType` value as well.</span></span> <span data-ttu-id="ee891-174">完成的類別定義看起來類似下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="ee891-174">The finished class definition looks like the following code:</span></span>

[!code-csharp[DefineQuestion](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

<span data-ttu-id="ee891-175">新增建構函式會移除警告。</span><span class="sxs-lookup"><span data-stu-id="ee891-175">Adding the constructor removes the warning.</span></span> <span data-ttu-id="ee891-176">建構函式引數也是不可為 Null 的參考類型，因次，編譯器不會發出任何警告。</span><span class="sxs-lookup"><span data-stu-id="ee891-176">The constructor argument is also a non-nullable reference type, so the compiler doesn't issue any warnings.</span></span>

<span data-ttu-id="ee891-177">接著，建立名為 `SurveyRun` 的 `public` 類別。</span><span class="sxs-lookup"><span data-stu-id="ee891-177">Next, create a `public` class named `SurveyRun`.</span></span> <span data-ttu-id="ee891-178">在 `using` 陳述式後面包含 `#nullable enable` pragma。</span><span class="sxs-lookup"><span data-stu-id="ee891-178">Include the `#nullable enable` pragma following the `using` statements.</span></span> <span data-ttu-id="ee891-179">這個類別包含 `SurveyQuestion` 物件和方法的清單，可在問卷中新增問題，如下列程式碼所示：</span><span class="sxs-lookup"><span data-stu-id="ee891-179">This class contains a list of `SurveyQuestion` objects and methods to add questions to the survey, as shown in the following code:</span></span>

```csharp
using System.Collections.Generic;

#nullable enable
namespace NullableIntroduction
{
    public class SurveyRun
    {
        private List<SurveyQuestion> surveyQuestions = new List<SurveyQuestion>();

        public void AddQuestion(QuestionType type, string question) =>
            AddQuestion(new SurveyQuestion(type, question));
        public void AddQuestion(SurveyQuestion surveyQuestion) => surveyQuestions.Add(surveyQuestion);
    }
}
```

<span data-ttu-id="ee891-180">和以前一樣，您必須將清單物件初始化為非 Null 的值，否則編譯器會發出警告。</span><span class="sxs-lookup"><span data-stu-id="ee891-180">As before, you must initialize the list object to a non-null value or the compiler issues a warning.</span></span> <span data-ttu-id="ee891-181">不會在 `AddQuestion` 的第二個多載中進行任何 Null 檢查，因為不需要：您已將該變數宣告成不可為 Null。</span><span class="sxs-lookup"><span data-stu-id="ee891-181">There are no null checks in the second overload of `AddQuestion` because they aren't needed: You've declared that variable to be non-nullable.</span></span> <span data-ttu-id="ee891-182">其值不可以是 `null`。</span><span class="sxs-lookup"><span data-stu-id="ee891-182">Its value can't be `null`.</span></span>

<span data-ttu-id="ee891-183">在編輯器中切換至 `Program.cs`，並使用下列程式碼行來取代 `Main` 的內容：</span><span class="sxs-lookup"><span data-stu-id="ee891-183">Switch to `Program.cs` in your editor and replace the contents of `Main` with the following lines of code:</span></span>

[!code-csharp[AddQuestions](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

<span data-ttu-id="ee891-184">如果檔案頂端沒有 `#nullable enable` pragma，則當您傳遞 `null` 作為 `AddQuestion` 引數的文字時，編譯器不會發出警告。</span><span class="sxs-lookup"><span data-stu-id="ee891-184">Without the `#nullable enable` pragma at the top of the file, the compiler doesn't issue a warning when you pass `null` as the text for the `AddQuestion` argument.</span></span> <span data-ttu-id="ee891-185">在 `using` 陳述式後面新增 `#nullable enable` 來修正該問題。</span><span class="sxs-lookup"><span data-stu-id="ee891-185">Fix that by adding `#nullable enable` following the `using` statement.</span></span> <span data-ttu-id="ee891-186">將下列這一行新增到 `Main` 來試用它：</span><span class="sxs-lookup"><span data-stu-id="ee891-186">Try it by adding the following line to `Main`:</span></span>

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a><span data-ttu-id="ee891-187">建立受訪者並取得問卷的答案</span><span class="sxs-lookup"><span data-stu-id="ee891-187">Create respondents and get answers to the survey</span></span>

<span data-ttu-id="ee891-188">接著，撰寫程式碼來產生問卷的答案。</span><span class="sxs-lookup"><span data-stu-id="ee891-188">Next, write the code that generates answers to the survey.</span></span> <span data-ttu-id="ee891-189">這牽涉到數個小型工作：</span><span class="sxs-lookup"><span data-stu-id="ee891-189">This involves several small tasks:</span></span>

1. <span data-ttu-id="ee891-190">建置方法來產生受訪者物件。</span><span class="sxs-lookup"><span data-stu-id="ee891-190">Build a method that generates respondent objects.</span></span> <span data-ttu-id="ee891-191">這些物件代表系統要求您填寫問卷的人員。</span><span class="sxs-lookup"><span data-stu-id="ee891-191">These represent people asked to fill out the survey.</span></span>
1. <span data-ttu-id="ee891-192">建置邏輯來模擬向受訪者詢問問題，然後收集答案，或記下受訪者沒有回答。</span><span class="sxs-lookup"><span data-stu-id="ee891-192">Build logic to simulate asking the questions to a respondent and collecting answers or noting that a respondent didn't answer.</span></span>
1. <span data-ttu-id="ee891-193">重複執行，直到有足夠的受訪者回答問卷為止。</span><span class="sxs-lookup"><span data-stu-id="ee891-193">Repeat until enough respondents have answered the survey.</span></span>

<span data-ttu-id="ee891-194">您需要一個類型來代表問卷回應，所以現在要新增該類別。</span><span class="sxs-lookup"><span data-stu-id="ee891-194">You'll need a class to represent a survey response, so add that now.</span></span> <span data-ttu-id="ee891-195">啟用可為 Null 的支援。</span><span class="sxs-lookup"><span data-stu-id="ee891-195">Enable nullable support.</span></span> <span data-ttu-id="ee891-196">新增 `Id` 屬性和建構函式來將它初始化，如下列程式碼所示：</span><span class="sxs-lookup"><span data-stu-id="ee891-196">Add an `Id` property and a constructor that initializes it, as shown in the following code:</span></span>

```csharp
#nullable enable
namespace NullableIntroduction
{
    public class SurveyResponse
    {
        public int Id { get; }

        public SurveyResponse(int id) => Id = id;
    }
}
```

<span data-ttu-id="ee891-197">接著，新增 `static` 方法，藉由產生隨機識別碼來建立新的參與者：</span><span class="sxs-lookup"><span data-stu-id="ee891-197">Next, add a `static` method to create new participants by generating a random ID:</span></span>

[!code-csharp[GenerateRespondents](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

<span data-ttu-id="ee891-198">這個類別的主要責任是產生參與者對問卷問題所做的回應。</span><span class="sxs-lookup"><span data-stu-id="ee891-198">The main responsibility of this class is to generate the responses for a participant to the questions in the survey.</span></span> <span data-ttu-id="ee891-199">這個責任有數個步驟：</span><span class="sxs-lookup"><span data-stu-id="ee891-199">This responsibility has a few steps:</span></span>

1. <span data-ttu-id="ee891-200">要求參與問卷。</span><span class="sxs-lookup"><span data-stu-id="ee891-200">Ask for participation in the survey.</span></span> <span data-ttu-id="ee891-201">如果該人員不同意，請傳回遺漏 (或 Null) 回應。</span><span class="sxs-lookup"><span data-stu-id="ee891-201">If the person doesn't consent, return a missing (or null) response.</span></span>
1. <span data-ttu-id="ee891-202">詢問每個問題並記錄答案。</span><span class="sxs-lookup"><span data-stu-id="ee891-202">Ask each question and record the answer.</span></span> <span data-ttu-id="ee891-203">每個答案也可能遺漏 (或 Null)。</span><span class="sxs-lookup"><span data-stu-id="ee891-203">Each answer may also be missing (or null).</span></span>

<span data-ttu-id="ee891-204">將下列程式碼新增至 `SurveyRespondent` 類別：</span><span class="sxs-lookup"><span data-stu-id="ee891-204">Add the following code to your `SurveyRespondent` class:</span></span>

[!code-csharp[AnswerSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

<span data-ttu-id="ee891-205">問卷答案的儲存體是 `Dictionary<int, string>?`，指出它可能是 Null。</span><span class="sxs-lookup"><span data-stu-id="ee891-205">The storage for the survey answers is a `Dictionary<int, string>?`, indicating that it may be null.</span></span> <span data-ttu-id="ee891-206">您正在使用新的語言功能，來向編譯器和稍後要讀取您程式碼的任何人宣告您的設計意圖。</span><span class="sxs-lookup"><span data-stu-id="ee891-206">You're using the new language feature to declare your design intent, both to the compiler and to anyone reading your code later.</span></span> <span data-ttu-id="ee891-207">如果您總是在未先檢查 Null 值的情況下為 `surveyResponses` 取值，將收到編譯器警告。</span><span class="sxs-lookup"><span data-stu-id="ee891-207">If you ever dereference `surveyResponses` without checking for the null value first, you'll get a compiler warning.</span></span> <span data-ttu-id="ee891-208">您不會在 `AnswerSurvey` 方法中收到警告，因為編譯器可判斷並未將 `surveyResponses` 變數設定為上述的非 Null 值。</span><span class="sxs-lookup"><span data-stu-id="ee891-208">You don't get a warning in the `AnswerSurvey` method because the compiler can determine the `surveyResponses` variable was set to a non-null value above.</span></span>

<span data-ttu-id="ee891-209">接著，您需要在 `SurveyRun` 類別中撰寫 `PerformSurvey` 方法。</span><span class="sxs-lookup"><span data-stu-id="ee891-209">Next, you need to write the `PerformSurvey` method in the `SurveyRun` class.</span></span> <span data-ttu-id="ee891-210">在 `SurveyRun` 類別中新增下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="ee891-210">Add the following code in the `SurveyRun` class:</span></span>

[!code-csharp[PerformSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

<span data-ttu-id="ee891-211">同樣地，您對於可為 Null 之 `List<SurveyResponse>?` 的選擇，表示回應可能是 Null。</span><span class="sxs-lookup"><span data-stu-id="ee891-211">Here again, your choice of a nullable `List<SurveyResponse>?` indicates the response may be null.</span></span> <span data-ttu-id="ee891-212">這表示尚未將問卷提供給任何受訪者。</span><span class="sxs-lookup"><span data-stu-id="ee891-212">That indicates the survey hasn't been given to any respondents yet.</span></span> <span data-ttu-id="ee891-213">請注意，受訪者會持續新增，直到有足夠的受訪者同意為止。</span><span class="sxs-lookup"><span data-stu-id="ee891-213">Notice that respondents are added until enough have consented.</span></span>

<span data-ttu-id="ee891-214">執行問卷的最後一個步驟是在 `Main` 方法的結尾處新增執行問卷的呼叫：</span><span class="sxs-lookup"><span data-stu-id="ee891-214">The last step to run the survey is to add a call to perform the survey at the end of the `Main` method:</span></span>

[!code-csharp[RunSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a><span data-ttu-id="ee891-215">檢查問卷回應</span><span class="sxs-lookup"><span data-stu-id="ee891-215">Examine survey responses</span></span>

<span data-ttu-id="ee891-216">最後一個步驟是顯示問卷結果。</span><span class="sxs-lookup"><span data-stu-id="ee891-216">The last step is to display survey results.</span></span> <span data-ttu-id="ee891-217">您將在所撰寫的多個類別中新增程式碼。</span><span class="sxs-lookup"><span data-stu-id="ee891-217">You'll add code to many of the classes you've written.</span></span> <span data-ttu-id="ee891-218">此程式碼示範用來區別可為 Null 與不可為 Null 之參考類型的值。</span><span class="sxs-lookup"><span data-stu-id="ee891-218">This code demonstrates the value of distinguishing nullable and non-nullable reference types.</span></span> <span data-ttu-id="ee891-219">一開始，請將下列兩個運算式主體成員新增至 `SurveyResponse` 類別：</span><span class="sxs-lookup"><span data-stu-id="ee891-219">Start by adding the following two expression-bodied members to the `SurveyResponse` class:</span></span>

[!code-csharp[ReportResponses](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

<span data-ttu-id="ee891-220">由於 `surveyResponses` 是不可為 Null 的參考類型，所以在為它取值之前不需要進行任何檢查。</span><span class="sxs-lookup"><span data-stu-id="ee891-220">Because `surveyResponses` is a non-nullable reference, type no checks are necessary before de-referencing it.</span></span> <span data-ttu-id="ee891-221">`Answer` 方法會傳回不可為 Null 的字串，因此，請選擇 `GetValueOrDefault` 的多載，以採用第二個引數作為預設值。</span><span class="sxs-lookup"><span data-stu-id="ee891-221">The `Answer` method returns a non-nullable string, so choose the overload of `GetValueOrDefault` that takes a second argument for the default value.</span></span>

<span data-ttu-id="ee891-222">接著，將這三個運算式主體成員新增到 `SurveyRun` 類別：</span><span class="sxs-lookup"><span data-stu-id="ee891-222">Next, add these three expression-bodied members to the `SurveyRun` class:</span></span>

[!code-csharp[ReportResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

<span data-ttu-id="ee891-223">`AllParticipants` 成員必須將下列因素納入考量：`respondents` 變數可能是 Null，但傳回的值不可為 Null。</span><span class="sxs-lookup"><span data-stu-id="ee891-223">The `AllParticipants` member must take into account that the `respondents` variable might be null, but the return value can't be null.</span></span> <span data-ttu-id="ee891-224">如果您藉由移除 `??` 及其後的空序列來變更該運算式，則編譯器會警告您方法可能傳回 `null`，而它的傳回簽章會傳回不可為 Null 的類型。</span><span class="sxs-lookup"><span data-stu-id="ee891-224">If you change that expression by removing the `??` and the empty sequence that follows, the compiler warns you the method might return `null` and its return signature returns a non-nullable type.</span></span>

<span data-ttu-id="ee891-225">最後，在 `Main` 方法的底部新增下列迴圈：</span><span class="sxs-lookup"><span data-stu-id="ee891-225">Finally, add the following loop at the bottom of the `Main` method:</span></span>

[!code-csharp[DisplaySurveyResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

<span data-ttu-id="ee891-226">您不需要在這個程式碼中進行任何 `null` 檢查，由於您已設計了基礎介面，因此它們全部都會傳回不可為 Null 的參考類型。</span><span class="sxs-lookup"><span data-stu-id="ee891-226">You don't need any `null` checks in this code because you've designed the underlying interfaces so that they all return non-nullable reference types.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="ee891-227">取得程式碼</span><span class="sxs-lookup"><span data-stu-id="ee891-227">Get the code</span></span>

<span data-ttu-id="ee891-228">您可以從 [csharp/IntroToNullables](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) 資料夾的[範例](https://github.com/dotnet/samples) \(英文\) 存放庫中取得已完成之教學課程的程式碼。</span><span class="sxs-lookup"><span data-stu-id="ee891-228">You can get the code for the finished tutorial from our [samples](https://github.com/dotnet/samples) repository in the [csharp/IntroToNullables](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) folder.</span></span>

<span data-ttu-id="ee891-229">藉由在可為 Null 與不可為 Null 的參考類型之間變更類型宣告來進行實驗。</span><span class="sxs-lookup"><span data-stu-id="ee891-229">Experiment by changing the type declarations between nullable and non-nullable reference types.</span></span> <span data-ttu-id="ee891-230">請參閱如何產生不同的警告以確保您不會意外地為 `null` 取值。</span><span class="sxs-lookup"><span data-stu-id="ee891-230">See how that generates different warnings to ensure you don't accidentally dereference a `null`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ee891-231">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ee891-231">Next steps</span></span>

<span data-ttu-id="ee891-232">請參閱＜可為 Null 的參考類型概觀＞進行深入了解。</span><span class="sxs-lookup"><span data-stu-id="ee891-232">Learn more by reading an overview of nullable reference types..</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="ee891-233">可為 Null 的參考概觀</span><span class="sxs-lookup"><span data-stu-id="ee891-233">An overview of nullable references</span></span>](../nullable-references.md)