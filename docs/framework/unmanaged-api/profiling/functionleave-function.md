---
title: FunctionLeave 函式
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 238a5f19bd8cbd89a5537b2b9297bfa9e1f54613
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952878"
---
# <a name="functionleave-function"></a>FunctionLeave 函式
通知分析工具, 函式即將傳回給呼叫者。  
  
> [!NOTE]
> `FunctionLeave`函數在 .NET Framework 2.0 中已被取代。 它會繼續工作, 但會造成效能上的負面影響。 請改用[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)函數。  
  
## <a name="syntax"></a>語法  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>參數  
 `funcID`  
 在傳回之函式的識別碼。  
  
## <a name="remarks"></a>備註  
 `FunctionLeave`函式是回呼; 您必須加以執行。 此執行必須使用`__declspec`(`naked`) 儲存類別屬性。  
  
 在呼叫此函式之前, 執行引擎不會儲存任何暫存器。  
  
- 輸入時, 您必須儲存您所使用的所有暫存器, 包括浮點單位 (FPU) 中的暫存器。  
  
- 結束時, 您必須透過關閉其呼叫者推送的所有參數來還原堆疊。  
  
 的執行`FunctionLeave`不應該封鎖, 因為它會延遲垃圾收集。 執行不應嘗試垃圾收集, 因為堆疊可能不會處於垃圾收集的唯讀狀態。 如果嘗試垃圾收集, 執行時間將會封鎖, 直到`FunctionLeave`傳回為止。  
  
 此外, 函`FunctionLeave`式不能呼叫 managed 程式碼, 或以任何方式執行 managed 記憶體配置。  
  
## <a name="requirements"></a>需求  
 **平台：** 請參閱[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorProf.idl  
  
 **LIBRARY:** CorGuids.lib  
  
 **.NET Framework 版本:** 1.1、1。0  
  
## <a name="see-also"></a>另請參閱

- [FunctionEnter2 函式](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2 函式](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [FunctionTailcall2 函式](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [分析全域靜態函式](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
