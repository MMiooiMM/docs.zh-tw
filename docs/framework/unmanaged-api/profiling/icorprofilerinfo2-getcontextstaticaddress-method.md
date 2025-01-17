---
title: ICorProfilerInfo2::GetContextStaticAddress 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2c5c8165d44cc3a305820f8e97c07da37f2a0693
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775802"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a>ICorProfilerInfo2::GetContextStaticAddress 方法
取得在指定之內容的範圍中指定內容靜態欄位的位址。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>參數  
 `classId`  
 [in]包含要求的內容靜態欄位的類別識別碼。  
  
 `fieldToken`  
 [in]要求的內容靜態欄位的中繼資料語彙基元。  
  
 `contextId`  
 [in]要求的內容靜態欄位的範圍的內容識別碼。  
  
 `ppAddress`  
 [out]在指定的內容內的靜態欄位的位址指標。  
  
## <a name="remarks"></a>備註  
 `GetContextStaticAddress`方法可能會傳回下列其中之一：  
  
- 如果指定的靜態欄位尚未指派指定的內容中的地址 CORPROF_E_DATAINCOMPLETE HRESULT。  
  
- 可能在記憶體回收堆積中物件的位址。 這些位址可能會變成無效記憶體回收之後，讓記憶體回收之後, 程式碼剖析工具不應該假設其有效。  
  
 類別的類別建構函式完成之前，`GetContextStaticAddress`雖然靜態欄位的一些可能已經初始化，將會傳回 CORPROF_E_DATAINCOMPLETE 所有其靜態欄位，及根廢棄項目集合物件。  
  
## <a name="requirements"></a>需求  
 **平台：** 請參閱[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorProf.idl, CorProf.h  
  
 **LIBRARY:** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另請參閱

- [ICorProfilerInfo 介面](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 介面](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
