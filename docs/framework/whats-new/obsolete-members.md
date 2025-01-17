---
title: 過時的成員 - .NET Framework
ms.custom: updateeachrelease
ms.date: 10/17/2017
helpviewer_keywords:
- .NET Framework, obsolete members
- members, obsolete in .NET Framework
- obsolete members [.NET Framework]
ms.assetid: 0ee25062-4071-4d3c-a552-87a75d3ecd34
ms.openlocfilehash: 2231552f9c3353890963a4ad5388194036fa27bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134093"
---
# <a name="obsolete-members-in-the-net-framework"></a>.NET Framework 中過時的成員

本文中的表格列出 .NET Framework 4.5 和更新版本中依組件分組的已淘汰類型成員。 請使用下列連結，查看每個組件中過時的成員和建議的替代做法清單。 本文不會列出過時的類型成員。 如需過時的型別清單，請參閱[已淘汰類型](obsolete-types.md)。

- [系統組件中過時的成員](#SystemMembers)

  - [mscorlib.dll](#mscorlib)

  - [PresentationCore.dll](#PresentationCore)

  - [PresentationFramework.dll](#PresFW)

  - [System.Activities.dll](#Act)

  - [System.Activities.Presentation.dll](#ActPres)

  - [System.Core.dll](#core)

  - [System.Data.dll](#data)

  - [System.Data.Entity.dll](#entity)

  - [System.Data.OracleClient.dll](#oracleclient)

  - [System.Design.dll](#design)

  - [System.dll](#system)

  - [System.Drawing.dll](#drawing)

  - [System.Messaging.dll](#messaging)

  - [System.ServiceModel.dll](#servicemodel)

  - [System.ServiceModel.Discovery.dll](#smDisc)

  - [System.Web.DataVisualization.dll](#datavisualization)

  - [System.Web.dll](#web)

  - [System.Web.DynamicData.dll](#dynamicdata)

  - [System.Web.Extensions.dll](#extensions)

  - [System.Web.Services.dll](#services)

  - [System.Windows.Forms.dll](#forms)

  - [System.Xaml.dll](#xaml)

  - [System.Xml.dll](#xml)

- [Microsoft 組件中過時的成員](#MicrosoftMembers)

  - [IEHost.dll 和 IEExec.exe](#IEHost)

  - [ISymWrapper.dll](#isymwrapper)

  - [Microsoft.Build.Conversion.v4.0.dll](#conversion)

  - [Microsoft.Build.Engine.dll](#engine)

  - [Microsoft.Build.Framework.dll](#BuildFW)

  - [Microsoft.Build.Utilities.v4.0.dll](#BuildUtil4)

  - [Microsoft.Data.Entity.Build.Tasks.dll](#data_entity_tasks)

  - [Microsoft.VisualBasic.dll](#visualbasic)

<a name="SystemMembers"></a>

## <a name="obsolete-members-in-system-assemblies"></a>系統組件中過時的成員

下表列出系統組件中過時的成員。 這些組件是用於以 .NET Framework 為目標的一般用途應用程式開發。

<a name="mscorlib"></a>

### <a name="assembly-mscorlibdll"></a>組件：mscorlib.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:Microsoft.Win32.Registry?displayProperty=nameWithType>|<xref:Microsoft.Win32.Registry.DynData>|<xref:Microsoft.Win32.Registry.DynData> 登錄機碼僅適用於 Win9x，不再受到 CLR 的支援。 在 NT 架構的作業系統上，請改用 <xref:Microsoft.Win32.Registry.PerformanceData?displayProperty=nameWithType> 登錄機碼或 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy.PerformanceData%2A?displayProperty=nameWithType> 登錄 Proxy。|
|<xref:System.Activator?displayProperty=nameWithType>|<xref:System.Activator.CreateInstance%28System.AppDomain%2CSystem.String%2CSystem.String%2CSystem.Boolean%2CSystem.Reflection.BindingFlags%2CSystem.Reflection.Binder%2CSystem.Object%5B%5D%2CSystem.Globalization.CultureInfo%2CSystem.Object%5B%5D%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的                                          <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> 多載。|
|<xref:System.Activator?displayProperty=nameWithType>|<xref:System.Activator.CreateInstance%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Reflection.BindingFlags%2CSystem.Reflection.Binder%2CSystem.Object%5B%5D%2CSystem.Globalization.CultureInfo%2CSystem.Object%5B%5D%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的                                          <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> 多載。|
|<xref:System.Activator?displayProperty=nameWithType>|<xref:System.Activator.CreateInstanceFrom%28System.AppDomain%2CSystem.String%2CSystem.String%2CSystem.Boolean%2CSystem.Reflection.BindingFlags%2CSystem.Reflection.Binder%2CSystem.Object%5B%5D%2CSystem.Globalization.CultureInfo%2CSystem.Object%5B%5D%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的                                          <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType> 多載。|
|<xref:System.Activator?displayProperty=nameWithType>|<xref:System.Activator.CreateInstanceFrom%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Reflection.BindingFlags%2CSystem.Reflection.Binder%2CSystem.Object%5B%5D%2CSystem.Globalization.CultureInfo%2CSystem.Object%5B%5D%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.AppendPrivatePath%2A>|<xref:System.AppDomain.AppendPrivatePath%2A> 已被取代。 請改為查看 <xref:System.AppDomainSetup.PrivateBinPath%2A?displayProperty=nameWithType> 的用法。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.ClearPrivatePath%2A>|<xref:System.AppDomain.ClearPrivatePath%2A> 已被取代。 請改為查看 <xref:System.AppDomainSetup.PrivateBinPath%2A?displayProperty=nameWithType> 的用法。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.ClearShadowCopyPath%2A>|<xref:System.AppDomain.ClearShadowCopyPath%2A> 已被取代。 請改為查看 <xref:System.AppDomainSetup.ShadowCopyDirectories%2A?displayProperty=nameWithType> 的用法。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.CreateInstance%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Reflection.BindingFlags%2CSystem.Reflection.Binder%2CSystem.Object%5B%5D%2CSystem.Globalization.CultureInfo%2CSystem.Object%5B%5D%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.CreateInstanceAndUnwrap%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Reflection.BindingFlags%2CSystem.Reflection.Binder%2CSystem.Object%5B%5D%2CSystem.Globalization.CultureInfo%2CSystem.Object%5B%5D%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.CreateInstanceFrom%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Reflection.BindingFlags%2CSystem.Reflection.Binder%2CSystem.Object%5B%5D%2CSystem.Globalization.CultureInfo%2CSystem.Object%5B%5D%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.CreateInstanceFromAndUnwrap%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Reflection.BindingFlags%2CSystem.Reflection.Binder%2CSystem.Object%5B%5D%2CSystem.Globalization.CultureInfo%2CSystem.Object%5B%5D%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.CreateInstanceFromAndUnwrap%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.DefineDynamicAssembly%28System.Reflection.AssemblyName%2CSystem.Reflection.Emit.AssemblyBuilderAccess%2CSystem.Security.Policy.Evidence%29>|組件層級宣告式安全性已過期，CLR 預設不再強制使用。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.DefineDynamicAssembly%28System.Reflection.AssemblyName%2CSystem.Reflection.Emit.AssemblyBuilderAccess%2CSystem.Security.Policy.Evidence%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%29>|組件層級宣告式安全性已過期，CLR 預設不再強制使用。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.DefineDynamicAssembly%28System.Reflection.AssemblyName%2CSystem.Reflection.Emit.AssemblyBuilderAccess%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%29>|組件層級宣告式安全性已過期，CLR 預設不再強制使用。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.DefineDynamicAssembly%28System.Reflection.AssemblyName%2CSystem.Reflection.Emit.AssemblyBuilderAccess%2CSystem.String%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.DefineDynamicAssembly%28System.Reflection.AssemblyName%2CSystem.Reflection.Emit.AssemblyBuilderAccess%2CSystem.String%2CSystem.Security.Policy.Evidence%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%29>|組件層級宣告式安全性已過期，CLR 預設不再強制使用。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.DefineDynamicAssembly%28System.Reflection.AssemblyName%2CSystem.Reflection.Emit.AssemblyBuilderAccess%2CSystem.String%2CSystem.Security.Policy.Evidence%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%2CSystem.Boolean%29>|組件層級宣告式安全性已過期，CLR 預設不再強制使用。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.DefineDynamicAssembly%28System.Reflection.AssemblyName%2CSystem.Reflection.Emit.AssemblyBuilderAccess%2CSystem.String%2CSystem.Security.Policy.Evidence%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%2CSystem.Boolean%2CSystem.Collections.Generic.IEnumerable%7BSystem.Reflection.Emit.CustomAttributeBuilder%7D%29>|組件層級宣告式安全性已過期，CLR 預設不再強制使用。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.DefineDynamicAssembly%28System.Reflection.AssemblyName%2CSystem.Reflection.Emit.AssemblyBuilderAccess%2CSystem.String%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%29>|組件層級宣告式安全性已過期，CLR 預設不再強制使用。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.String%5B%5D%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.ExecuteAssemblyByName%28System.Reflection.AssemblyName%2CSystem.Security.Policy.Evidence%2CSystem.String%5B%5D%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.ExecuteAssemblyByName%28System.String%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.ExecuteAssemblyByName%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.String%5B%5D%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.GetCurrentThreadId%2A>|<xref:System.AppDomain.GetCurrentThreadId%2A> 已過時，因為當受控執行緒在 Fiber (也稱為輕量型執行緒) 上執行時，它無法提供固定識別碼。 若要取得 Managed 執行緒的固定識別碼，請使用 <xref:System.Threading.Thread.ManagedThreadId%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.Load%28System.Reflection.AssemblyName%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.Load%28System.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.Load%28System.String%2CSystem.Security.Policy.Evidence%29>|對沙箱使用辨識項的方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> 多載。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.SetAppDomainPolicy%2A>|<xref:System.AppDomain> 原則層級已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.SetCachePath%2A>|<xref:System.AppDomain.SetCachePath%2A> 已被取代。 請改為查看 <xref:System.AppDomainSetup.CachePath%2A?displayProperty=nameWithType> 的用法。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.SetDynamicBase%2A>|<xref:System.AppDomain.SetDynamicBase%2A> 已被取代。 請改為查看 <xref:System.AppDomainSetup.DynamicBase%2A?displayProperty=nameWithType> 的用法。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.SetShadowCopyFiles%2A>|<xref:System.AppDomain.SetShadowCopyFiles%2A> 已被取代。 請改為查看 <xref:System.AppDomainSetup.ShadowCopyFiles%2A?displayProperty=nameWithType> 的用法。|
|<xref:System.AppDomain?displayProperty=nameWithType>|<xref:System.AppDomain.SetShadowCopyPath%2A>|<xref:System.AppDomain.SetShadowCopyPath%2A> 已被取代。 請改為查看 <xref:System.AppDomainSetup.ShadowCopyDirectories%2A?displayProperty=nameWithType> 的用法。|
|<xref:System.Enum?displayProperty=nameWithType>|<xref:System.Enum.ToString(System.IFormatProvider)>|不使用 `provider` 引數。 使用 <xref:System.Enum.ToString?displayProperty=nameWithType>。|
|<xref:System.Enum?displayProperty=nameWithType>|<xref:System.Enum.ToString(System.String,System.IFormatProvider)>|不使用 `provider` 引數。 使用 <xref:System.Enum.ToString(System.String)?displayProperty=nameWithType>。|
|<xref:System.LoaderOptimization?displayProperty=nameWithType>|<xref:System.LoaderOptimization.DisallowBindings>|這個方法已被取代。 請改用 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 。|
|<xref:System.LoaderOptimization?displayProperty=nameWithType>|<xref:System.LoaderOptimization.DomainMask>|這個方法已被取代。 請改用 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 。|
|<xref:System.Collections.Hashtable?displayProperty=nameWithType>|<xref:System.Collections.Hashtable.%23ctor%28System.Collections.IDictionary%2CSystem.Collections.IHashCodeProvider%2CSystem.Collections.IComparer%29>|請改用 <xref:System.Collections.Hashtable.%23ctor%28System.Collections.IDictionary%2CSystem.Collections.IEqualityComparer%29?displayProperty=nameWithType> 。|
|<xref:System.Collections.Hashtable?displayProperty=nameWithType>|<xref:System.Collections.Hashtable.%23ctor%28System.Collections.IHashCodeProvider%2CSystem.Collections.IComparer%29>|請改用 <xref:System.Collections.Hashtable.%23ctor%28System.Collections.IEqualityComparer%29?displayProperty=nameWithType> 。|
|<xref:System.Collections.Hashtable?displayProperty=nameWithType>|<xref:System.Collections.Hashtable.%23ctor%28System.Int32%2CSystem.Collections.IHashCodeProvider%2CSystem.Collections.IComparer%29>|請改用 <xref:System.Collections.Hashtable.%23ctor%28System.Int32%2CSystem.Collections.IEqualityComparer%29?displayProperty=nameWithType> 。|
|<xref:System.Collections.Hashtable?displayProperty=nameWithType>|<xref:System.Collections.Hashtable.%23ctor%28System.Int32%2CSystem.Single%2CSystem.Collections.IHashCodeProvider%2CSystem.Collections.IComparer%29>|請改用 <xref:System.Collections.Hashtable.%23ctor%28System.Int32%2CSystem.Single%2CSystem.Collections.IEqualityComparer%29?displayProperty=nameWithType> 。|
|<xref:System.Collections.Hashtable?displayProperty=nameWithType>|<xref:System.Collections.Hashtable.comparer%2A?displayProperty=nameWithType>|請使用 <xref:System.Collections.Hashtable.EqualityComparer%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.Collections.Hashtable?displayProperty=nameWithType>|<xref:System.Collections.Hashtable.hcp%2A?displayProperty=nameWithType>|使用 `KeyComparer` 屬性。|
|<xref:System.Collections.Hashtable?displayProperty=nameWithType>|<xref:System.Collections.Hashtable.%23ctor%28System.Collections.IDictionary%2CSystem.Single%2CSystem.Collections.IHashCodeProvider%2CSystem.Collections.IComparer%29>|請改用 <xref:System.Collections.Hashtable.%23ctor%28System.Collections.IDictionary%2CSystem.Single%2CSystem.Collections.IEqualityComparer%29?displayProperty=nameWithType> 。|
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType>|<xref:System.Configuration.Assemblies.AssemblyHash.Algorithm%2A>|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType> 類別已被取代。|
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType>|<xref:System.Configuration.Assemblies.AssemblyHash.%23ctor%28System.Configuration.Assemblies.AssemblyHashAlgorithm%2CSystem.Byte%5B%5D%29>|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType> 類別已被取代。|
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType>|<xref:System.Configuration.Assemblies.AssemblyHash.%23ctor%28System.Byte%5B%5D%29>|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType> 類別已被取代。|
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType>|<xref:System.Configuration.Assemblies.AssemblyHash.Clone%2A>|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType> 類別已被取代。|
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType>|<xref:System.Configuration.Assemblies.AssemblyHash.Empty>|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType> 類別已被取代。|
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType>|<xref:System.Configuration.Assemblies.AssemblyHash.GetValue%2A>|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType> 類別已被取代。|
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType>|<xref:System.Configuration.Assemblies.AssemblyHash.SetValue%2A>|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType> 類別已被取代。|
|<xref:System.Diagnostics.Debugger?displayProperty=nameWithType>|<xref:System.Diagnostics.Debugger.%23ctor%2A>|請勿建立 <xref:System.Diagnostics.Debugger> 類別的執行個體。 請改為直接針對這個類型呼叫靜態方法。|
|<xref:System.Diagnostics.StackTrace?displayProperty=nameWithType>|<xref:System.Diagnostics.StackTrace.%23ctor%28System.Threading.Thread%2CSystem.Boolean%29>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 這個建構函式已被取代。 請使用不需要 <xref:System.Threading.Thread> 參數的建構函式。|
|<xref:System.Diagnostics.SymbolStore.ISymbolBinder?displayProperty=nameWithType>|<xref:System.Diagnostics.SymbolStore.ISymbolBinder.GetReader%2A>|建議的替代做法是 <xref:System.Diagnostics.SymbolStore.ISymbolBinder1.GetReader%2A?displayProperty=nameWithType>，它會接受匯入工具介面指標當做 <xref:System.IntPtr> 而不是 <xref:System.Int32>，因此可同時在 32 位元和 64 位元架構上運作。|
|<xref:System.Globalization.CultureTypes?displayProperty=nameWithType>|<xref:System.Globalization.CultureTypes.FrameworkCultures>|這個值已被取代。 請使用 <xref:System.Globalization.CultureTypes?displayProperty=nameWithType> 中的其他值。|
|<xref:System.Globalization.CultureTypes?displayProperty=nameWithType>|<xref:System.Globalization.CultureTypes.WindowsOnlyCultures>|這個值已被取代。 請使用 <xref:System.Globalization.CultureTypes?displayProperty=nameWithType> 中的其他值。|
|<xref:System.IO.FileStream?displayProperty=nameWithType>|<xref:System.IO.FileStream.%23ctor%28System.IntPtr%2CSystem.IO.FileAccess%29>|這個建構函式已被取代。 請改用 <xref:System.IO.FileStream.%23ctor%28Microsoft.Win32.SafeHandles.SafeFileHandle%2CSystem.IO.FileAccess%29?displayProperty=nameWithType> 。|
|<xref:System.IO.FileStream?displayProperty=nameWithType>|<xref:System.IO.FileStream.%23ctor%28System.IntPtr%2CSystem.IO.FileAccess%2CSystem.Boolean%29>|這個建構函式已被取代。 請改用 <xref:System.IO.FileStream.%23ctor%28Microsoft.Win32.SafeHandles.SafeFileHandle%2CSystem.IO.FileAccess%29?displayProperty=nameWithType>，並選擇性地視需要使用 `ownsHandle`= `false` 來建立新的 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle?displayProperty=nameWithType>。|
|<xref:System.IO.FileStream?displayProperty=nameWithType>|<xref:System.IO.FileStream.%23ctor%28System.IntPtr%2CSystem.IO.FileAccess%2CSystem.Boolean%2CSystem.Int32%29>|這個建構函式已被取代。 請改用 <xref:System.IO.FileStream.%23ctor%28Microsoft.Win32.SafeHandles.SafeFileHandle%2CSystem.IO.FileAccess%2CSystem.Int32%29?displayProperty=nameWithType>，並選擇性地視需要使用 `ownsHandle`= `false` 來建立新的 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle?displayProperty=nameWithType>。|
|<xref:System.IO.FileStream?displayProperty=nameWithType>|<xref:System.IO.FileStream.%23ctor%28System.IntPtr%2CSystem.IO.FileAccess%2CSystem.Boolean%2CSystem.Int32%2CSystem.Boolean%29>|這個建構函式已被取代。 請改用 <xref:System.IO.FileStream.%23ctor%28Microsoft.Win32.SafeHandles.SafeFileHandle%2CSystem.IO.FileAccess%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=nameWithType>，並選擇性地視需要使用 `ownsHandle`= `false` 來建立新的 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle?displayProperty=nameWithType>。|
|<xref:System.IO.FileStream?displayProperty=nameWithType>|<xref:System.IO.FileStream.Handle%2A>|這個屬性已被取代。 請改用 <xref:System.IO.FileStream.SafeFileHandle%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.IO.Path?displayProperty=nameWithType>|<xref:System.IO.Path.InvalidPathChars>|請改用 <xref:System.IO.Path.GetInvalidPathChars%2A?displayProperty=nameWithType> 或 <xref:System.IO.Path.GetInvalidFileNameChars%2A?displayProperty=nameWithType>。|
|<xref:System.IO.Stream?displayProperty=nameWithType>|<xref:System.IO.Stream.CreateWaitHandle%2A>|<xref:System.IO.Stream.CreateWaitHandle%2A> 最終將會被移除。 請改用 `new ManualResetEvent(false)` 。|
|<xref:System.IO.Stream?displayProperty=nameWithType>|<xref:System.IO.Stream.ObjectInvariant%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 請勿呼叫或覆寫這個方法。|
|<xref:System.IO.IsolatedStorage.IsolatedStorage?displayProperty=nameWithType>|<xref:System.IO.IsolatedStorage.IsolatedStorage.CurrentSize%2A>|<xref:System.IO.IsolatedStorage.IsolatedStorage.CurrentSize%2A> 已過時，因為它不符合 CLS 標準。 若要取得目前大小，請使用 <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A?displayProperty=nameWithType>。|
|<xref:System.IO.IsolatedStorage.IsolatedStorage?displayProperty=nameWithType>|<xref:System.IO.IsolatedStorage.IsolatedStorage.MaximumSize%2A>|<xref:System.IO.IsolatedStorage.IsolatedStorage.MaximumSize%2A> 已過時，因為它不符合 CLS 標準。 若要取得大小上限，請使用 <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A?displayProperty=nameWithType>。|
|<xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>|<xref:System.IO.IsolatedStorage.IsolatedStorageFile.CurrentSize%2A>|<xref:System.IO.IsolatedStorage.IsolatedStorageFile.CurrentSize%2A> 已過時，因為它不符合 CLS 標準。 若要取得目前大小，請使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.UsedSize%2A>。|
|<xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>|<xref:System.IO.IsolatedStorage.IsolatedStorageFile.MaximumSize%2A>|<xref:System.IO.IsolatedStorage.IsolatedStorageFile.MaximumSize%2A> 已過時，因為它不符合 CLS 標準。 若要取得大小上限，請使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Quota%2A?displayProperty=nameWithType>。|
|<xref:System.IO.IsolatedStorage.IsolatedStorageFileStream?displayProperty=nameWithType>|<xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.Handle%2A>|這個屬性已被取代。 請改用 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.SafeFileHandle%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.Reflection.Assembly?displayProperty=nameWithType>|<xref:System.Reflection.Assembly.Load%28System.Reflection.AssemblyName%2CSystem.Security.Policy.Evidence%29>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 多載。|
|<xref:System.Reflection.Assembly?displayProperty=nameWithType>|<xref:System.Reflection.Assembly.Load%28System.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Security.Policy.Evidence%29>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 多載。|
|<xref:System.Reflection.Assembly?displayProperty=nameWithType>|<xref:System.Reflection.Assembly.Load%28System.String%2CSystem.Security.Policy.Evidence%29>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 多載。|
|<xref:System.Reflection.Assembly?displayProperty=nameWithType>|<xref:System.Reflection.Assembly.LoadFile%28System.String%2CSystem.Security.Policy.Evidence%29>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> 多載。|
|<xref:System.Reflection.Assembly?displayProperty=nameWithType>|<xref:System.Reflection.Assembly.LoadFrom%28System.String%2CSystem.Security.Policy.Evidence%29>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> 多載。|
|<xref:System.Reflection.Assembly?displayProperty=nameWithType>|<xref:System.Reflection.Assembly.LoadFrom%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> 多載。|
|<xref:System.Reflection.Assembly?displayProperty=nameWithType>|<xref:System.Reflection.Assembly.LoadWithPartialName%28System.String%29>|這個方法已被取代。 請改用 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 。|
|<xref:System.Reflection.Assembly?displayProperty=nameWithType>|<xref:System.Reflection.Assembly.LoadWithPartialName%28System.String%2CSystem.Security.Policy.Evidence%29>|這個方法已被取代。 請改用 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 。|
|<xref:System.Reflection.AssemblyFlagsAttribute?displayProperty=nameWithType>|<xref:System.Reflection.AssemblyFlagsAttribute.%23ctor%28System.Int32%29>|這個建構函式已被取代。 請改用 <xref:System.Reflection.AssemblyFlagsAttribute.%23ctor%28System.Reflection.AssemblyNameFlags%29?displayProperty=nameWithType> 。|
|<xref:System.Reflection.AssemblyFlagsAttribute?displayProperty=nameWithType>|<xref:System.Reflection.AssemblyFlagsAttribute.%23ctor%28System.UInt32%29>|這個建構函式已被取代。 請改用 <xref:System.Reflection.AssemblyFlagsAttribute.%23ctor%28System.Reflection.AssemblyNameFlags%29?displayProperty=nameWithType> 。|
|<xref:System.Reflection.AssemblyFlagsAttribute?displayProperty=nameWithType>|<xref:System.Reflection.AssemblyFlagsAttribute.Flags%2A>|這個屬性已被取代。 請改用 <xref:System.Reflection.AssemblyFlagsAttribute.AssemblyFlags%2A?displayProperty=nameWithType> 。|
|<xref:System.Reflection.Emit.ConstructorBuilder?displayProperty=nameWithType>|<xref:System.Reflection.Emit.ConstructorBuilder.ReturnType%2A>|這個屬性已被取代。|
|<xref:System.Reflection.Emit.FieldBuilder?displayProperty=nameWithType>|<xref:System.Reflection.Emit.FieldBuilder.SetMarshal%2A>|有替代的 API 可用：請改為發出 <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> 自訂屬性。|
|<xref:System.Reflection.Emit.FlowControl?displayProperty=nameWithType>|<xref:System.Reflection.Emit.FlowControl.Phi>|這個 API 已被取代。|
|<xref:System.Reflection.Emit.MethodBuilder?displayProperty=nameWithType>|<xref:System.Reflection.Emit.MethodBuilder.SetMarshal%2A>|有替代的 API 可用：請改為發出 <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> 自訂屬性。|
|<xref:System.Reflection.Emit.OpCodeType?displayProperty=nameWithType>|<xref:System.Reflection.Emit.OpCodeType.Annotation>|這個 API 已被取代。|
|<xref:System.Reflection.Emit.OperandType?displayProperty=nameWithType>|<xref:System.Reflection.Emit.OperandType.InlinePhi>|這個 API 已被取代。|
|<xref:System.Reflection.Emit.ParameterBuilder?displayProperty=nameWithType>|<xref:System.Reflection.Emit.ParameterBuilder.SetMarshal%2A>|有替代的 API 可用：請改為發出 <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> 自訂屬性。|
|<xref:System.Resources.ResourceManager?displayProperty=nameWithType>|<xref:System.Resources.ResourceManager.ResourceSets>|請改為呼叫 <xref:System.Resources.ResourceManager.InternalGetResourceSet%28System.Globalization.CultureInfo%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=nameWithType>。|
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetManagedThunkForUnmanagedMethodPtr%2A>|<xref:System.Runtime.InteropServices.Marshal.GetManagedThunkForUnmanagedMethodPtr%2A> 方法已被取代，將在未來的版本中移除。|
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetThreadFromFiberCookie%2A>|<xref:System.Runtime.InteropServices.Marshal.GetThreadFromFiberCookie%2A> 方法已被取代。 請使用裝載 API 來執行這項作業。|
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetTypeInfoName%28System.Runtime.InteropServices.UCOMITypeInfo%29>|請改用 <xref:System.Runtime.InteropServices.Marshal.GetTypeInfoName%28System.Runtime.InteropServices.ComTypes.ITypeInfo%29?displayProperty=nameWithType> 。|
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetTypeLibGuid%28System.Runtime.InteropServices.UCOMITypeLib%29>|請改用 <xref:System.Runtime.InteropServices.Marshal.GetTypeLibGuid%28System.Runtime.InteropServices.ComTypes.ITypeLib%29?displayProperty=nameWithType> 。|
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetTypeLibLcid%28System.Runtime.InteropServices.UCOMITypeLib%29>|請改用 <xref:System.Runtime.InteropServices.Marshal.GetTypeLibLcid%28System.Runtime.InteropServices.ComTypes.ITypeLib%29?displayProperty=nameWithType> 。|
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetTypeLibName%28System.Runtime.InteropServices.UCOMITypeLib%29>|請改用 <xref:System.Runtime.InteropServices.Marshal.GetTypeLibName%28System.Runtime.InteropServices.ComTypes.ITypeLib%29?displayProperty=nameWithType> 。|
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetUnmanagedThunkForManagedMethodPtr%2A>|<xref:System.Runtime.InteropServices.Marshal.GetUnmanagedThunkForManagedMethodPtr%2A> 方法已被取代，將在未來的版本中移除。|
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReleaseThreadCache%2A>|這個 API 不會執行任何作業，將在未來的 CLR 版本中移除。|
|<xref:System.Runtime.InteropServices.RuntimeEnvironment?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.RuntimeEnvironment.%23ctor%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿建立 <xref:System.Runtime.InteropServices.RuntimeEnvironment?displayProperty=nameWithType> 類別的執行個體。 請改為直接針對這個類型呼叫靜態方法。|
|<xref:System.Runtime.Remoting.Channels.ChannelServices?displayProperty=nameWithType>|<xref:System.Runtime.Remoting.Channels.ChannelServices.RegisterChannel%2A>|請改用 <xref:System.Runtime.Remoting.Channels.ChannelServices.RegisterChannel%28System.Runtime.Remoting.Channels.IChannel%2CSystem.Boolean%29?displayProperty=nameWithType> 。|
|<xref:System.Runtime.Remoting.Lifetime.LifetimeServices?displayProperty=nameWithType>|<xref:System.Runtime.Remoting.Lifetime.LifetimeServices.%23ctor%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿建立 <xref:System.Runtime.Remoting.Lifetime.LifetimeServices> 類別的執行個體。 請改為直接針對這個類型呼叫靜態方法。|
|<xref:System.Runtime.Remoting.RemotingConfiguration?displayProperty=nameWithType>|<xref:System.Runtime.Remoting.RemotingConfiguration.Configure%28System.String%29>|請改用 <xref:System.Runtime.Remoting.RemotingConfiguration.Configure%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> 。|
|<xref:System.Runtime.Remoting.RemotingServices?displayProperty=nameWithType>|<xref:System.Runtime.Remoting.RemotingServices.LogRemotingStage%2A>|不建議使用這個方法。 <xref:System.Runtime.Remoting.RemotingServices.LogRemotingStage%2A> 僅供內部診斷之用。|
|<xref:System.Security.CodeAccessPermission?displayProperty=nameWithType>|<xref:System.Security.CodeAccessPermission.Deny%2A>|<xref:System.Security.CodeAccessPermission.Deny%2A> 已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.CodeAccessPermission?displayProperty=nameWithType>|<xref:System.Security.CodeAccessPermission.RevertDeny%2A>|<xref:System.Security.CodeAccessPermission.Deny%2A> 已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.HostSecurityManager?displayProperty=nameWithType>|<xref:System.Security.HostSecurityManager.DomainPolicy%2A>|AppDomain 原則層級已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.HostSecurityManagerOptions?displayProperty=nameWithType>|<xref:System.Security.HostSecurityManagerOptions.HostPolicyLevel>|AppDomain 原則層級已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.PermissionSet?displayProperty=nameWithType>|<xref:System.Security.PermissionSet.ConvertPermissionSet%2A>|這個方法已經過時，不應再使用。|
|<xref:System.Security.PermissionSet?displayProperty=nameWithType>|<xref:System.Security.PermissionSet.Deny%2A>|<xref:System.Security.PermissionSet.Deny%2A> 已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.SecurityCriticalAttribute?displayProperty=nameWithType>|<xref:System.Security.SecurityCriticalAttribute.Scope%2A>|<xref:System.Security.SecurityCriticalScope?displayProperty=nameWithType> 僅用於 .NET 2.0 透明度相容性。|
|<xref:System.Security.SecurityManager?displayProperty=nameWithType>|<xref:System.Security.SecurityManager.CheckExecutionRights%2A>|由於無法再關閉執行權限檢查，因此 <xref:System.Security.SecurityManager.CheckExecutionRights%2A> 屬性不再具有任何作用。|
|<xref:System.Security.SecurityManager?displayProperty=nameWithType>|<xref:System.Security.SecurityManager.IsGranted%2A>|<xref:System.Security.SecurityManager.IsGranted%2A> 已經過時，將在未來的 .NET Framework 版本中移除。 請改用 <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType> 屬性或 <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.Security.SecurityManager?displayProperty=nameWithType>|<xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.SecurityManager?displayProperty=nameWithType>|<xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.SecurityManager?displayProperty=nameWithType>|<xref:System.Security.SecurityManager.PolicyHierarchy%2A>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.SecurityManager?displayProperty=nameWithType>|<xref:System.Security.SecurityManager.ResolvePolicy%28System.Security.Policy.Evidence%29>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.SecurityManager?displayProperty=nameWithType>|<xref:System.Security.SecurityManager.ResolvePolicy%28System.Security.Policy.Evidence%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%2CSystem.Security.PermissionSet%40%29>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.SecurityManager?displayProperty=nameWithType>|<xref:System.Security.SecurityManager.ResolvePolicy%28System.Security.Policy.Evidence%5B%5D%29>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.SecurityManager?displayProperty=nameWithType>|<xref:System.Security.SecurityManager.ResolvePolicyGroups%2A>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.SecurityManager?displayProperty=nameWithType>|<xref:System.Security.SecurityManager.ResolveSystemPolicy%2A>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.SecurityManager?displayProperty=nameWithType>|<xref:System.Security.SecurityManager.SavePolicy%2A>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.SecurityManager?displayProperty=nameWithType>|<xref:System.Security.SecurityManager.SavePolicyLevel%2A>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.SecurityManager?displayProperty=nameWithType>|<xref:System.Security.SecurityManager.SecurityEnabled%2A>|由於無法再關閉安全性，因此 <xref:System.Security.SecurityManager.SecurityEnabled%2A> 屬性不再具有任何作用。|
|<xref:System.Security.Cryptography.PasswordDeriveBytes?displayProperty=nameWithType>|<xref:System.Security.Cryptography.PasswordDeriveBytes.GetBytes%2A>|<xref:System.Security.Cryptography.Rfc2898DeriveBytes?displayProperty=nameWithType> 會取代 <xref:System.Security.Cryptography.PasswordDeriveBytes?displayProperty=nameWithType>，以便從密碼中衍生金鑰內容，而且新的應用程式會優先使用它。|
|<xref:System.Security.Cryptography.X509Certificates.X509Certificate?displayProperty=nameWithType>|<xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetIssuerName%2A>|這個方法已被取代。 請改用 <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Issuer%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.Security.Cryptography.X509Certificates.X509Certificate?displayProperty=nameWithType>|<xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetName%2A>|這個方法已被取代。 請改用 <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Subject%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.Security.Permissions.FileIOPermissionAttribute?displayProperty=nameWithType>|<xref:System.Security.Permissions.FileIOPermissionAttribute.All%2A>|請改用 <xref:System.Security.Permissions.FileIOPermissionAttribute.ViewAndModify%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.Security.Permissions.ReflectionPermissionAttribute?displayProperty=nameWithType>|<xref:System.Security.Permissions.ReflectionPermissionAttribute.ReflectionEmit%2A>|CLR 已不再使用這個權限。|
|<xref:System.Security.Permissions.ReflectionPermissionAttribute?displayProperty=nameWithType>|<xref:System.Security.Permissions.ReflectionPermissionAttribute.TypeInformation%2A>|這個 API 已被取代。|
|<xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=nameWithType>|<xref:System.Security.Permissions.ReflectionPermissionFlag.AllFlags>|這個權限已被取代。 <xref:System.Security.Permissions.ReflectionPermissionFlag.AllFlags> 列舉成員不包含 <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess>。 請使用 <xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType> 來取得完整存取權。|
|<xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=nameWithType>|<xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>|CLR 已不再使用這個權限。|
|<xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=nameWithType>|<xref:System.Security.Permissions.ReflectionPermissionFlag.TypeInformation>|這個 API 已被取代。|
|<xref:System.Security.Permissions.RegistryPermissionAttribute?displayProperty=nameWithType>|<xref:System.Security.Permissions.RegistryPermissionAttribute.All%2A>|請改用 <xref:System.Security.Permissions.RegistryPermissionAttribute.ViewAndModify%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.Security.Permissions.SecurityAction?displayProperty=nameWithType>|<xref:System.Security.Permissions.SecurityAction.Deny>|<xref:System.Security.Permissions.SecurityAction.Deny> 已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.Permissions.SecurityAction?displayProperty=nameWithType>|<xref:System.Security.Permissions.SecurityAction.RequestMinimum>|組件層級宣告式安全性已過期，CLR 預設不再強制使用。|
|<xref:System.Security.Permissions.SecurityAction?displayProperty=nameWithType>|<xref:System.Security.Permissions.SecurityAction.RequestOptional>|組件層級宣告式安全性已過期，CLR 預設不再強制使用。|
|<xref:System.Security.Permissions.SecurityAction?displayProperty=nameWithType>|<xref:System.Security.Permissions.SecurityAction.RequestRefuse>|組件層級宣告式安全性已過期，CLR 預設不再強制使用。|
|<xref:System.Security.Policy.Evidence?displayProperty=nameWithType>|<xref:System.Security.Policy.Evidence.AddAssembly%2A>|這個方法已過時。 請改用 <xref:System.Security.Policy.Evidence.AddAssemblyEvidence%2A?displayProperty=nameWithType> 。|
|<xref:System.Security.Policy.Evidence?displayProperty=nameWithType>|<xref:System.Security.Policy.Evidence.AddHost%2A>|這個方法已過時。 請改用 <xref:System.Security.Policy.Evidence.AddHostEvidence%2A?displayProperty=nameWithType> 。|
|<xref:System.Security.Policy.Evidence?displayProperty=nameWithType>|<xref:System.Security.Policy.Evidence.CopyTo%2A>|辨識項不應該被視為 <xref:System.Collections.ICollection?displayProperty=nameWithType>。 請使用 <xref:System.Security.Policy.Evidence.GetHostEnumerator%2A?displayProperty=nameWithType> 和 <xref:System.Security.Policy.Evidence.GetAssemblyEnumerator%2A?displayProperty=nameWithType> 方法，而不是使用 <xref:System.Security.Policy.Evidence.CopyTo%2A>。|
|<xref:System.Security.Policy.Evidence?displayProperty=nameWithType>|<xref:System.Security.Policy.Evidence.Count%2A>|辨識項不應該被視為 <xref:System.Collections.ICollection?displayProperty=nameWithType>。 請使用 <xref:System.Security.Policy.Evidence.GetHostEnumerator%2A?displayProperty=nameWithType> 和 <xref:System.Security.Policy.Evidence.GetAssemblyEnumerator%2A?displayProperty=nameWithType> 來反覆查看辨識項，以便收集計數。|
|<xref:System.Security.Policy.Evidence?displayProperty=nameWithType>|<xref:System.Security.Policy.Evidence.%23ctor%28System.Object%5B%5D%2CSystem.Object%5B%5D%29>|這個建構函式已經過時。 請改用 <xref:System.Security.Policy.Evidence.%23ctor%28System.Security.Policy.EvidenceBase%5B%5D%2CSystem.Security.Policy.EvidenceBase%5B%5D%29?displayProperty=nameWithType> 建構函式。|
|<xref:System.Security.Policy.Evidence?displayProperty=nameWithType>|<xref:System.Security.Policy.Evidence.GetEnumerator%2A>|<xref:System.Security.Policy.Evidence.GetEnumerator%2A> 已經過時。 請改用 <xref:System.Security.Policy.Evidence.GetHostEnumerator%2A?displayProperty=nameWithType> 和 <xref:System.Security.Policy.Evidence.GetAssemblyEnumerator%2A?displayProperty=nameWithType>。|
|<xref:System.Security.Policy.PolicyLevel?displayProperty=nameWithType>|<xref:System.Security.Policy.PolicyLevel.AddFullTrustAssembly%28System.Security.Policy.StrongName%29>|由於所有 GAC 組件一律都會取得完全信任，因此完全信任清單已不再有意義。 您應該在 GAC 中安裝安全性原則所使用的任何組件，以確保這些組件是受信任的組件。|
|<xref:System.Security.Policy.PolicyLevel?displayProperty=nameWithType>|<xref:System.Security.Policy.PolicyLevel.AddFullTrustAssembly%28System.Security.Policy.StrongNameMembershipCondition%29>|由於所有 GAC 組件一律都會取得完全信任，因此完全信任清單已不再有意義。 您應該在 GAC 中安裝安全性原則所使用的任何組件，以確保這些組件是受信任的組件。|
|<xref:System.Security.Policy.PolicyLevel?displayProperty=nameWithType>|<xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A>|AppDomain 原則層級已經過時，將在未來的 .NET Framework 版本中移除。|
|<xref:System.Security.Policy.PolicyLevel?displayProperty=nameWithType>|<xref:System.Security.Policy.PolicyLevel.FullTrustAssemblies%2A>|由於所有 GAC 組件一律都會取得完全信任，因此完全信任清單已不再有意義。 您應該在 GAC 中安裝安全性原則所使用的任何組件，以確保這些組件是受信任的組件。|
|<xref:System.Security.Policy.PolicyLevel?displayProperty=nameWithType>|<xref:System.Security.Policy.PolicyLevel.RemoveFullTrustAssembly%28System.Security.Policy.StrongName%29>|由於所有 GAC 組件一律都會取得完全信任，因此完全信任清單已不再有意義。 您應該在 GAC 中安裝安全性原則所使用的任何組件，以確保這些組件是受信任的組件。|
|<xref:System.Security.Policy.PolicyLevel?displayProperty=nameWithType>|<xref:System.Security.Policy.PolicyLevel.RemoveFullTrustAssembly%28System.Security.Policy.StrongNameMembershipCondition%29>|由於所有 GAC 組件一律都會取得完全信任，因此完全信任清單已不再有意義。 您應該在 GAC 中安裝安全性原則所使用的任何組件，以確保這些組件是受信任的組件。|
|<xref:System.Threading.Overlapped?displayProperty=nameWithType>|<xref:System.Threading.Overlapped.EventHandle%2A>|這個屬性與 64 位元不相容。 請改用 <xref:System.Threading.Overlapped.EventHandleIntPtr%2A?displayProperty=nameWithType> 。|
|<xref:System.Threading.Overlapped?displayProperty=nameWithType>|<xref:System.Threading.Overlapped.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.IAsyncResult%29>|這個建構函式與 64 位元不相容。 請針對事件處理常式使用採用 <xref:System.IntPtr?displayProperty=nameWithType> 的 <xref:System.Threading.Overlapped.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.IntPtr%2CSystem.IAsyncResult%29?displayProperty=nameWithType> 建構函式。|
|<xref:System.Threading.Overlapped?displayProperty=nameWithType>|<xref:System.Threading.Overlapped.Pack%28System.Threading.IOCompletionCallback%29>|這個方法不安全。 請改用 <xref:System.Threading.Overlapped.Pack%28System.Threading.IOCompletionCallback%2CSystem.Object%29?displayProperty=nameWithType> 。|
|<xref:System.Threading.Overlapped?displayProperty=nameWithType>|<xref:System.Threading.Overlapped.UnsafePack%28System.Threading.IOCompletionCallback%29>|這個方法不安全。 請改用 <xref:System.Threading.Overlapped.UnsafePack%28System.Threading.IOCompletionCallback%2CSystem.Object%29?displayProperty=nameWithType> 。|
|<xref:System.Threading.Thread?displayProperty=nameWithType>|<xref:System.Threading.Thread.ApartmentState%2A>|<xref:System.Threading.Thread.ApartmentState%2A> 屬性已被取代。 請改用 <xref:System.Threading.Thread.GetApartmentState%2A?displayProperty=nameWithType>、<xref:System.Threading.Thread.SetApartmentState%2A?displayProperty=nameWithType> 或 <xref:System.Threading.Thread.TrySetApartmentState%2A?displayProperty=nameWithType>。|
|<xref:System.Threading.Thread?displayProperty=nameWithType>|<xref:System.Threading.Thread.GetCompressedStack%2A>|<xref:System.Threading.Thread.GetCompressedStack%2A> 不再受支援。 使用 <xref:System.Threading.CompressedStack?displayProperty=nameWithType> 類別。|
|<xref:System.Threading.Thread?displayProperty=nameWithType>|<xref:System.Threading.Thread.Resume%2A>|<xref:System.Threading.Thread.Resume%2A> 已被取代。 請使用 <xref:System.Threading?displayProperty=nameWithType> 中的其他類別 (例如 <xref:System.Threading.Monitor>、<xref:System.Threading.Mutex>、<xref:System.Threading.EventWaitHandle> 和 <xref:System.Threading.Semaphore>) 來同步處理執行緒或保護資源。|
|<xref:System.Threading.Thread?displayProperty=nameWithType>|<xref:System.Threading.Thread.SetCompressedStack%2A>|<xref:System.Threading.Thread.SetCompressedStack%2A> 不再受支援。 使用 <xref:System.Threading.CompressedStack?displayProperty=nameWithType> 類別。|
|<xref:System.Threading.Thread?displayProperty=nameWithType>|<xref:System.Threading.Thread.Suspend%2A>|<xref:System.Threading.Thread.Suspend%2A> 已被取代。 請使用 <xref:System.Threading?displayProperty=nameWithType> 中的其他類別 (例如 <xref:System.Threading.Monitor>、<xref:System.Threading.Mutex>、<xref:System.Threading.EventWaitHandle> 和 <xref:System.Threading.Semaphore>) 來同步處理執行緒或保護資源。|
|<xref:System.Threading.ThreadPool?displayProperty=nameWithType>|<xref:System.Threading.ThreadPool.BindHandle%28System.IntPtr%29>|<xref:System.Threading.ThreadPool.BindHandle%28System.IntPtr%29> 已被取代。 請改用 <xref:System.Threading.ThreadPool.BindHandle%28System.Runtime.InteropServices.SafeHandle%29?displayProperty=nameWithType> 。|
|<xref:System.Threading.WaitHandle?displayProperty=nameWithType>|<xref:System.Threading.WaitHandle.Handle%2A>|請改用 <xref:System.Threading.WaitHandle.SafeWaitHandle%2A?displayProperty=nameWithType> 屬性。|

<a name="PresentationCore"></a>

### <a name="assembly-presentationcoredll"></a>組件：PresentationCore.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Windows.UIElement?displayProperty=nameWithType>|<xref:System.Windows.UIElement.BitmapEffect%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.UIElement?displayProperty=nameWithType>|<xref:System.Windows.UIElement.BitmapEffectInput%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.UIElement?displayProperty=nameWithType>|<xref:System.Windows.UIElement.PersistId%2A>|<xref:System.Windows.UIElement.PersistId%2A> 是過時的屬性，可能在未來的版本中移除。 未定義此屬性的值。|
|<xref:System.Windows.Media.ContainerVisual?displayProperty=nameWithType>|<xref:System.Windows.Media.ContainerVisual.BitmapEffect%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.ContainerVisual?displayProperty=nameWithType>|<xref:System.Windows.Media.ContainerVisual.BitmapEffectInput%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.DrawingContext?displayProperty=nameWithType>|<xref:System.Windows.Media.DrawingContext.PushEffect%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.FormattedText?displayProperty=nameWithType>|<xref:System.Windows.Media.FormattedText.%23ctor(System.String,System.Globalization.CultureInfo,System.Windows.FlowDirection,System.Windows.Media.Typeface,System.Double,System.Windows.Media.Brush)?displayProperty=nameWithType>|使用 PixelsPerDip 覆寫。|
|<xref:System.Windows.Media.FormattedText?displayProperty=nameWithType>|<xref:System.Windows.Media.FormattedText.%23ctor(System.String,System.Globalization.CultureInfo,System.Windows.FlowDirection,System.Windows.Media.Typeface,System.Double,System.Windows.Media.Brush,System.Windows.Media.NumberSubstitution)>|使用 PixelsPerDip 覆寫。|
|<xref:System.Windows.Media.FormattedText?displayProperty=nameWithType>|<xref:System.Windows.Media.FormattedText.%23ctor(System.String,System.Globalization.CultureInfo,System.Windows.FlowDirection,System.Windows.Media.Typeface,System.Double,System.Windows.Media.Brush,System.Windows.Media.NumberSubstitution,System.Windows.Media.TextFormattingMode)>|使用 PixelsPerDip 覆寫。|
|<xref:System.Windows.Media.GlyphRun?displayProperty=nameWithType>|<xref:System.Windows.Media.GlyphRun.%23ctor>|使用 PixelsPerDip 覆寫。|
|<xref:System.Windows.Media.GlyphRun?displayProperty=nameWithType>|<xref:System.Windows.Media.GlyphRun.%23ctor(System.Windows.Media.GlyphTypeface,System.Int32,System.Boolean,System.Double,System.Collections.Generic.IList{System.UInt16},System.Windows.Point,System.Collections.Generic.IList{System.Double},System.Collections.Generic.IList{System.Windows.Point},System.Collections.Generic.IList{System.Char},System.String,System.Collections.Generic.IList{System.UInt16},System.Collections.Generic.IList{System.Boolean},System.Windows.Markup.XmlLanguage)>|使用 PixelsPerDip 覆寫。|
|<xref:System.Windows.Media.RenderCapability?displayProperty=nameWithType>|<xref:System.Windows.Media.RenderCapability.IsShaderEffectSoftwareRenderingSupported%2A>|這個屬性已被取代。 請改用靜態 <xref:System.Windows.Media.RenderCapability.IsPixelShaderVersionSupportedInSoftware%2A?displayProperty=nameWithType> 方法。|
|<xref:System.Windows.Media.Visual?displayProperty=nameWithType>|<xref:System.Windows.Media.Visual.VisualBitmapEffect%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Visual?displayProperty=nameWithType>|<xref:System.Windows.Media.Visual.VisualBitmapEffectInput%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.BevelBitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.CreateUnmanagedEffect%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.BevelBitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.UpdateUnmanagedPropertyState%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.BitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.CreateBitmapEffectOuter%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.BitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.CreateUnmanagedEffect%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.BitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.GetOutput%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.BitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.InitializeBitmapEffect%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.BitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.SetValue%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.BitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.UpdateUnmanagedPropertyState%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.BitmapEffectGroup?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.CreateUnmanagedEffect%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.BitmapEffectGroup?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.UpdateUnmanagedPropertyState%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.BlurBitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.CreateUnmanagedEffect%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.BlurBitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.UpdateUnmanagedPropertyState%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.DropShadowBitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.CreateUnmanagedEffect%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.DropShadowBitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.UpdateUnmanagedPropertyState%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.EmbossBitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.CreateUnmanagedEffect%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.EmbossBitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.UpdateUnmanagedPropertyState%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.OuterGlowBitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.CreateUnmanagedEffect%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Effects.OuterGlowBitmapEffect?displayProperty=nameWithType>|<xref:System.Windows.Media.Effects.BitmapEffect.UpdateUnmanagedPropertyState%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Media3D.Viewport3DVisual?displayProperty=nameWithType>|<xref:System.Windows.Media.Media3D.Viewport3DVisual.BitmapEffect%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|
|<xref:System.Windows.Media.Media3D.Viewport3DVisual?displayProperty=nameWithType>|<xref:System.Windows.Media.Media3D.Viewport3DVisual.BitmapEffectInput%2A>|點陣圖效果已被取代而不再有效。 請考慮在適當時改用 <xref:System.Windows.Media.Effects.Effect?displayProperty=nameWithType>。|

<a name="PresFW"></a>
### <a name="assembly-presentationframeworkdll"></a>組件：PresentationFramework.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Windows.Data.BindingListCollectionView?displayProperty=nameWithType>|<xref:System.Windows.Data.CollectionView.OnBeginChangeLogging%2A>|取代成 <xref:System.Windows.Data.CollectionView.OnAllowsCrossThreadChangesChanged%2A?displayProperty=nameWithType>。|
|<xref:System.Windows.Data.CollectionView?displayProperty=nameWithType>|<xref:System.Windows.Data.CollectionView.ClearChangeLog%2A>|取代成 <xref:System.Windows.Data.CollectionView.ClearPendingChanges%2A?displayProperty=nameWithType>。|
|<xref:System.Windows.Data.CollectionView?displayProperty=nameWithType>|<xref:System.Windows.Data.CollectionView.OnBeginChangeLogging%2A>|取代成 <xref:System.Windows.Data.CollectionView.OnAllowsCrossThreadChangesChanged%2A?displayProperty=nameWithType>。|
|<xref:System.Windows.Data.ListCollectionView?displayProperty=nameWithType>|<xref:System.Windows.Data.ListCollectionView.OnBeginChangeLogging%2A>|取代成 <xref:System.Windows.Data.ListCollectionView.OnAllowsCrossThreadChangesChanged%2A?displayProperty=nameWithType>。|

<a name="Act"></a>

### <a name="assembly-systemactivitiesdll"></a>組件：System.Activities.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Activities.Debugger.XamlDebuggerXmlReader?displayProperty=nameWithType>|<xref:System.Activities.Debugger.XamlDebuggerXmlReader.%23ctor%28System.Xaml.XamlReader%2CSystem.Xaml.IXamlLineInfo%2CSystem.IO.TextReader%29>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 請勿使用這個建構函式。 請改用 <xref:System.Activities.Debugger.XamlDebuggerXmlReader.%23ctor%28System.IO.TextReader%29?displayProperty=nameWithType> 或 <xref:System.Activities.Debugger.XamlDebuggerXmlReader.%23ctor%28System.IO.TextReader%2CSystem.Xaml.XamlSchemaContext%29?displayProperty=nameWithType>。|
|<xref:System.Activities.Debugger.XamlDebuggerXmlReader?displayProperty=nameWithType>|<xref:System.Activities.Debugger.XamlDebuggerXmlReader.%23ctor%28System.Xaml.XamlReader%2CSystem.IO.TextReader%29?displayProperty=nameWithType>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 請勿使用這個建構函式。 請改用 <xref:System.Activities.Debugger.XamlDebuggerXmlReader.%23ctor%28System.IO.TextReader%29?displayProperty=nameWithType> 或 <xref:System.Activities.Debugger.XamlDebuggerXmlReader.%23ctor%28System.IO.TextReader%2CSystem.Xaml.XamlSchemaContext%29?displayProperty=nameWithType>。|

<a name="ActPres"></a>

### <a name="assembly-systemactivitiespresentationdll"></a>組件：System.Activities.Presentation.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Activities.Presentation.DragDropHelper?displayProperty=nameWithType>|<xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29>|這個方法不支援拖曳多個項目。|
|<xref:System.Activities.Presentation.DragDropHelper?displayProperty=nameWithType>|<xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Windows.DragEventArgs%29>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 這個方法不支援拖曳多個項目。 請改用 <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Activities.Presentation.WorkflowViewElement%29> 。|
|<xref:System.Activities.Presentation.DragDropHelper?displayProperty=nameWithType>|<xref:System.Activities.Presentation.DragDropHelper.GetDragDropCompletedEffects%2A>|這個方法不支援拖曳多個項目。|
|<xref:System.Activities.Presentation.DragDropHelper?displayProperty=nameWithType>|<xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 這個方法不支援拖曳多個項目。 請改用 <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItems%2A> 。|
|<xref:System.Activities.Presentation.DragDropHelper?displayProperty=nameWithType>|<xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 這個方法不支援拖曳多個項目。 請改用 <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObjects%2A> 。|
|<xref:System.Activities.Presentation.DragDropHelper?displayProperty=nameWithType>|<xref:System.Activities.Presentation.DragDropHelper.SetDragDropCompletedEffects%2A>|這個方法不支援拖曳多個項目。|
|<xref:System.Activities.Presentation.Services.ModelChangedEventArgs?displayProperty=nameWithType>|<xref:System.Activities.Presentation.Services.ModelChangedEventArgs.ItemsAdded%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 請勿使用這個屬性。 請改用 <xref:System.Activities.Presentation.Services.ModelChangedEventArgs.ModelChangeInfo%2A> 。|
|<xref:System.Activities.Presentation.Services.ModelChangedEventArgs?displayProperty=nameWithType>|<xref:System.Activities.Presentation.Services.ModelChangedEventArgs.ItemsRemoved%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 請勿使用這個屬性。 請改用 <xref:System.Activities.Presentation.Services.ModelChangedEventArgs.ModelChangeInfo%2A> 。|
|<xref:System.Activities.Presentation.Services.ModelChangedEventArgs?displayProperty=nameWithType>|<xref:System.Activities.Presentation.Services.ModelChangedEventArgs.PropertiesChanged%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 請勿使用這個屬性。 請改用 <xref:System.Activities.Presentation.Services.ModelChangedEventArgs.ModelChangeInfo%2A> 。|

<a name="core"></a>

### <a name="assembly-systemcoredll"></a>組件：System.Core.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Diagnostics.Eventing.Reader.StandardEventKeywords?displayProperty=nameWithType>|<xref:System.Diagnostics.Eventing.Reader.StandardEventKeywords.CorrelationHint>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 不正確的值；請改用 <xref:System.Diagnostics.Eventing.Reader.StandardEventKeywords.CorrelationHint2>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.Concat%60%601%28System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%600%7D%29>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.Except%60%601%28System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%600%7D%29>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.Except%60%601%28System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%600%7D%29>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.GroupJoin%60%604%28System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.GroupJoin%60%604%28System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D%29>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.Intersect%60%601%28System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%600%7D%29>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.Intersect%60%601%28System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%600%7D%29>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.Join%60%604%28System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.Join%60%604%28System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D%29>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.SequenceEqual%60%601%28System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%600%7D%29>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.SequenceEqual%60%601%28System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%600%7D%29>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.Union%60%601%28System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%600%7D%29>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.Union%60%601%28System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%600%7D%29>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>|<xref:System.Linq.ParallelEnumerable.Zip%2A>|二元運算子的第二個資料來源必須是 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType> 類型，而不是 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 若要修正這個問題，請使用 <xref:System.Linq.ParallelEnumerable.AsParallel%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 擴充方法將右邊資料來源轉換成 <xref:System.Linq.ParallelQuery%601?displayProperty=nameWithType>。|
|<xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>|<xref:System.Linq.Expressions.Expression.%23ctor%28System.Linq.Expressions.ExpressionType%2CSystem.Type%29>|使用未採用 <xref:System.Linq.Expressions.ExpressionType?displayProperty=nameWithType> 引數的其他建構函式。 然後覆寫 <xref:System.Linq.Expressions.Expression.NodeType%2A?displayProperty=nameWithType> 和 <xref:System.Linq.Expressions.Expression.Type%2A?displayProperty=nameWithType> 屬性，以提供指定給這個建構函式的值。|
|<xref:System.Linq.Expressions.MemberBinding?displayProperty=nameWithType>|<xref:System.Linq.Expressions.MemberBinding.%23ctor%2A>|請勿使用這個建構函式。 將在未來的版本中移除。|
|<xref:System.Runtime.CompilerServices.CallSiteOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.CallSiteOps.AddRule%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.CallSiteOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.CallSiteOps.Bind%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.CallSiteOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.CallSiteOps.ClearMatch%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.CallSiteOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.CallSiteOps.CreateMatchmaker%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.CallSiteOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.CallSiteOps.GetCachedRules%60%601%28System.Runtime.CompilerServices.RuleCache%7B%60%600%7D%29>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.CallSiteOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.CallSiteOps.GetMatch%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.CallSiteOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.CallSiteOps.GetRuleCache%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.CallSiteOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.CallSiteOps.GetRules%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.CallSiteOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.CallSiteOps.MoveRule%60%601%28System.Runtime.CompilerServices.RuleCache%7B%60%600%7D%2C%60%600%2CSystem.Int32%29>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.CallSiteOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.CallSiteOps.SetNotMatched%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.CallSiteOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.CallSiteOps.UpdateRules%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.RuntimeOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.RuntimeOps.CreateRuntimeVariables>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.RuntimeOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.RuntimeOps.CreateRuntimeVariables%28System.Object%5B%5D%2CSystem.Int64%5B%5D%29>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.RuntimeOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.RuntimeOps.ExpandoCheckVersion%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.RuntimeOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.RuntimeOps.ExpandoPromoteClass%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.RuntimeOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.RuntimeOps.ExpandoTryDeleteValue%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.RuntimeOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.RuntimeOps.ExpandoTryGetValue%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.RuntimeOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.RuntimeOps.ExpandoTrySetValue%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.RuntimeOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.RuntimeOps.MergeRuntimeVariables%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:System.Runtime.CompilerServices.RuntimeOps?displayProperty=nameWithType>|<xref:System.Runtime.CompilerServices.RuntimeOps.Quote%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|

<a name="data"></a>

### <a name="assembly-systemdatadll"></a>組件：System.Data.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Data.DataSysDescriptionAttribute?displayProperty=nameWithType>|<xref:System.Data.DataSysDescriptionAttribute.%23ctor%2A>|<xref:System.Data.DataSysDescriptionAttribute> 已被取代。|
|<xref:System.Data.Common.DataAdapter?displayProperty=nameWithType>|<xref:System.Data.Common.DataAdapter.CloneInternals%2A>|<xref:System.Data.Common.DataAdapter.CloneInternals%2A> 已被取代。 請使用 <xref:System.Data.Common.DataAdapter.%23ctor%28System.Data.Common.DataAdapter%29> 建構函式。|
|<xref:System.Data.Common.DBDataPermission?displayProperty=nameWithType>|<xref:System.Data.Common.DBDataPermission.%23ctor>|使用這個成員會產生編譯器錯誤。<br /><br /> 這個建構函式已被取代。 請將 <xref:System.Security.Permissions.PermissionState.None?displayProperty=nameWithType> 的值傳遞給 <xref:System.Data.Common.DBDataPermission.%23ctor%28System.Security.Permissions.PermissionState%29> 建構函式。|
|<xref:System.Data.Common.DBDataPermission?displayProperty=nameWithType>|<xref:System.Data.Common.DBDataPermission.%23ctor%28System.Security.Permissions.PermissionState%2CSystem.Boolean%29>|使用這個成員會產生編譯器錯誤。<br /><br /> 這個建構函式已被取代。 請將 <xref:System.Security.Permissions.PermissionState.None?displayProperty=nameWithType> 的值傳遞給 <xref:System.Data.Common.DBDataPermission.%23ctor%28System.Security.Permissions.PermissionState%29> 建構函式。|
|<xref:System.Data.Odbc.OdbcParameterCollection?displayProperty=nameWithType>|<xref:System.Data.Odbc.OdbcParameterCollection.Add%28System.String%2CSystem.Object%29>|<xref:System.Data.Odbc.OdbcParameterCollection.Add%28System.String%2CSystem.Object%29> 已被取代。 使用 <xref:System.Data.Odbc.OdbcParameterCollection.AddWithValue%28System.String%2CSystem.Object%29?displayProperty=nameWithType>。|
|<xref:System.Data.Odbc.OdbcPermission?displayProperty=nameWithType>|<xref:System.Data.Odbc.OdbcPermission.%23ctor>|使用這個成員會產生編譯器錯誤。<br /><br /> <xref:System.Data.Odbc.OdbcPermission.%23ctor> 已被取代。 請將 <xref:System.Security.Permissions.PermissionState.None?displayProperty=nameWithType> 的值傳遞給 <xref:System.Data.Odbc.OdbcPermission.%23ctor%28System.Security.Permissions.PermissionState%29> 建構函式。|
|<xref:System.Data.Odbc.OdbcPermission?displayProperty=nameWithType>|<xref:System.Data.Odbc.OdbcPermission.%23ctor%28System.Security.Permissions.PermissionState%2CSystem.Boolean%29>|使用這個成員會產生編譯器錯誤。<br /><br /> <xref:System.Data.Odbc.OdbcPermission.%23ctor%28System.Security.Permissions.PermissionState%2CSystem.Boolean%29> 已被取代。 請將 <xref:System.Security.Permissions.PermissionState.None?displayProperty=nameWithType> 的值傳遞給 <xref:System.Data.Odbc.OdbcPermission.%23ctor%28System.Security.Permissions.PermissionState%29> 建構函式。|
|<xref:System.Data.OleDb.OleDbParameterCollection?displayProperty=nameWithType>|<xref:System.Data.OleDb.OleDbParameterCollection.Add%28System.String%2CSystem.Object%29>|<xref:System.Data.OleDb.OleDbParameterCollection.Add%28System.String%2CSystem.Object%29> 已被取代。 請使用 <xref:System.Data.OleDb.OleDbParameterCollection.AddWithValue%2A?displayProperty=nameWithType> 方法。|
|<xref:System.Data.OleDb.OleDbPermission?displayProperty=nameWithType>|<xref:System.Data.OleDb.OleDbPermission.%23ctor>|使用這個成員會產生編譯器錯誤。<br /><br /> <xref:System.Data.OleDb.OleDbPermission.%23ctor> 已被取代。 請將 <xref:System.Security.Permissions.PermissionState.None?displayProperty=nameWithType> 的值傳遞給 <xref:System.Data.OleDb.OleDbPermission.%23ctor%28System.Security.Permissions.PermissionState%29>。|
|<xref:System.Data.OleDb.OleDbPermission?displayProperty=nameWithType>|<xref:System.Data.OleDb.OleDbPermission.%23ctor%28System.Security.Permissions.PermissionState%2CSystem.Boolean%29>|使用這個成員會產生編譯器錯誤。<br /><br /> <xref:System.Data.OleDb.OleDbPermission.%23ctor%28System.Security.Permissions.PermissionState%2CSystem.Boolean%29> 已被取代。 請將 <xref:System.Security.Permissions.PermissionState.None?displayProperty=nameWithType> 的值傳遞給 <xref:System.Data.OleDb.OleDbPermission.%23ctor%28System.Security.Permissions.PermissionState%29>。|
|<xref:System.Data.OleDb.OleDbPermission?displayProperty=nameWithType>|<xref:System.Data.OleDb.OleDbPermission.Provider%2A>|<xref:System.Data.OleDb.OleDbPermission.Provider?displayProperty=nameWithType> 屬性已被取代。 請使用 <xref:System.Data.Common.DBDataPermission.Add%28System.String%2CSystem.String%2CSystem.Data.KeyRestrictionBehavior%29?displayProperty=nameWithType> 方法。|
|<xref:System.Data.OleDb.OleDbPermissionAttribute?displayProperty=nameWithType>|<xref:System.Data.OleDb.OleDbPermissionAttribute.Provider%2A>|<xref:System.Data.OleDb.OleDbPermissionAttribute.Provider?displayProperty=nameWithType> 屬性已被取代。 請使用 <xref:System.Data.Common.DBDataPermission.Add%28System.String%2CSystem.String%2CSystem.Data.KeyRestrictionBehavior%29?displayProperty=nameWithType> 方法。|
|<xref:System.Data.SqlClient.SqlClientPermission?displayProperty=nameWithType>|<xref:System.Data.SqlClient.SqlClientPermission.%23ctor>|使用這個建構函式會產生編譯器錯誤。<br /><br /> <xref:System.Data.SqlClient.SqlClientPermission.%23ctor> 已被取代。 請將 <xref:System.Security.Permissions.PermissionState.None?displayProperty=nameWithType> 的值傳遞給 <xref:System.Data.SqlClient.SqlClientPermission.%23ctor%28System.Security.Permissions.PermissionState%29> 建構函式。|
|<xref:System.Data.SqlClient.SqlClientPermission?displayProperty=nameWithType>|<xref:System.Data.SqlClient.SqlClientPermission.%23ctor%28System.Security.Permissions.PermissionState%2CSystem.Boolean%29>|使用這個建構函式會產生編譯器錯誤。<br /><br /> <xref:System.Data.SqlClient.SqlClientPermission.%23ctor%28System.Security.Permissions.PermissionState%2CSystem.Boolean%29> 已被取代。 請將 <xref:System.Security.Permissions.PermissionState.None?displayProperty=nameWithType> 的值傳遞給 <xref:System.Data.SqlClient.SqlClientPermission.%23ctor%28System.Security.Permissions.PermissionState%29> 建構函式。|
|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectionReset%2A>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectionReset%2A> 已被取代。 <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> 將會忽略 'connection reset' 關鍵字，而且一律會重設連接。|
|<xref:System.Data.SqlClient.SqlParameterCollection?displayProperty=nameWithType>|<xref:System.Data.SqlClient.SqlParameterCollection.Add%28System.String%2CSystem.Object%29>|<xref:System.Data.SqlClient.SqlParameterCollection.Add%28System.String%2CSystem.Object%29> 已被取代。 使用 <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A?displayProperty=nameWithType>。|

<a name="entity"></a>

### <a name="assembly-systemdataentitydll"></a>組件：System.Data.Entity.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Data.Metadata.Edm.AssociationSetEnd?displayProperty=nameWithType>|<xref:System.Data.Metadata.Edm.AssociationSetEnd.Role%2A>|這個屬性即將消失，請改用 <xref:System.Data.Metadata.Edm.AssociationSetEnd.Name%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.Data.Metadata.Edm.MetadataWorkspace?displayProperty=nameWithType>|<xref:System.Data.Metadata.Edm.MetadataWorkspace.GetRequiredOriginalValueMembers%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 請改用 <xref:System.Data.Metadata.Edm.MetadataWorkspace.GetRelevantMembersForUpdate%2A?displayProperty=nameWithType> 。|
|<xref:System.Data.Objects.ObjectContext?displayProperty=nameWithType>|<xref:System.Data.Objects.ObjectContext.ApplyPropertyChanges%2A>|請改用 <xref:System.Data.Objects.ObjectContext.ApplyCurrentValues%2A?displayProperty=nameWithType> 。|
|<xref:System.Data.Objects.ObjectContext?displayProperty=nameWithType>|<xref:System.Data.Objects.ObjectContext.SaveChanges%28System.Boolean%29>|請改用 <xref:System.Data.Objects.ObjectContext.SaveChanges%28System.Data.Objects.SaveOptions%29> 。|

<a name="oracleclient"></a>

### <a name="assembly-systemdataoracleclientdll"></a>組件：System.Data.OracleClient.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Data.OracleClient.OracleParameter?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleParameter.Precision%2A>|<xref:System.Data.OracleClient.OracleParameter.Precision%2A> 已被取代。 請使用 <xref:System.Math?displayProperty=nameWithType> 類別來明確設定小數的有效位數。|
|<xref:System.Data.OracleClient.OracleParameter?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleParameter.Scale%2A>|<xref:System.Data.OracleClient.OracleParameter.Scale%2A> 已被取代。 請使用 <xref:System.Math?displayProperty=nameWithType> 類別來明確設定小數的小數位數。|
|<xref:System.Data.OracleClient.OracleParameterCollection?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleParameterCollection.Add%28System.String%2CSystem.Object%29>|<xref:System.Data.OracleClient.OracleParameterCollection.Add%28System.String%2CSystem.Object%29> 已被取代。 使用 <xref:System.Data.OracleClient.OracleParameterCollection.AddWithValue%2A?displayProperty=nameWithType>。|

<a name="design"></a>

### <a name="assembly-systemdesigndll"></a>組件：System.Design.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.ComponentModel.Design.ComponentDesigner?displayProperty=nameWithType>|<xref:System.ComponentModel.Design.ComponentDesigner.InitializeNonDefault%2A>|這個方法已被取代。 請改用 <xref:System.ComponentModel.Design.ComponentDesigner.InitializeExistingComponent%2A?displayProperty=nameWithType> 。|
|<xref:System.ComponentModel.Design.ComponentDesigner?displayProperty=nameWithType>|<xref:System.ComponentModel.Design.ComponentDesigner.OnSetComponentDefaults%2A>|這個方法已被取代。 請改用 <xref:System.ComponentModel.Design.ComponentDesigner.InitializeNewComponent%2A?displayProperty=nameWithType> 。|
|<xref:System.ComponentModel.Design.DesignSurface?displayProperty=nameWithType>|<xref:System.ComponentModel.Design.DesignSurface.CreateComponent%2A>|<xref:System.ComponentModel.Design.DesignSurface.CreateComponent%2A> 方法已由 <xref:System.ComponentModel.Design.DesignSurface.CreateInstance%28System.Type%29> 取代。|
|<xref:System.ComponentModel.Design.Serialization.CodeDomSerializer?displayProperty=nameWithType>|<xref:System.ComponentModel.Design.Serialization.CodeDomSerializer.SerializeToReferenceExpression%2A>|這個方法已被取代。 請改用 <xref:System.ComponentModel.Design.Serialization.CodeDomSerializerBase.SerializeToExpression%2A> 或 <xref:System.ComponentModel.Design.Serialization.CodeDomSerializerBase.GetExpression%2A>。|
|<xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.ControlDesigner.DesignTimeElementView%2A>|使用這個屬性會產生編譯器錯誤。<br /><br /> 錯誤：無法再參考這個屬性，但已將其加入來支援現有已編譯的應用程式。 不再使用設計階段項目檢視架構。|
|<xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.ControlDesigner.DesignTimeHtmlRequiresLoadComplete%2A>|建議的替代做法是使用 [`ControlDesigner.SetViewFlags(ViewFlags.DesignTimeHtmlRequiresLoadComplete, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.ControlDesigner.GetPersistInnerHtml%2A>|建議的替代做法是 <xref:System.Web.UI.Design.ControlDesigner.GetPersistenceContent%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.ControlDesigner.IsDirty%2A>|建議的替代做法是使用 [`ControlDesigner.Tag.SetDirty`](xref:System.Web.UI.Design.IControlDesignerTag.SetDirty%2A) 和 [`ControlDesigner.Tag.IsDirty`](xref:System.Web.UI.Design.IControlDesignerTag.IsDirty%2A)。|
|<xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.ControlDesigner.IsPropertyBound%2A>|建議的替代做法是 [`ControlDesigner.DataBindings.Contains`](xref:System.Web.UI.DataBindingCollection.Contains%2A)。 <xref:System.Web.UI.DataBindingCollection?displayProperty=nameWithType> 類別可讓您進一步控制與控制項關聯的資料繫結。|
|<xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.ControlDesigner.OnBindingsCollectionChanged%2A>|建議的替代做法是處理 `ControlDesigner.DataBindings.Changed` 事件。 [`ControlDesigner.DataBindings`](xref:System.Web.UI.Design.HtmlControlDesigner.DataBindings%2A) 屬性所傳回的 <xref:System.Web.UI.DataBindingCollection> 集合，可讓您進一步控制與控制項相關聯的資料繫結。|
|<xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.ControlDesigner.OnControlResize%2A>|建議的替代做法是 <xref:System.Web.UI.Design.ControlDesigner.OnComponentChanged%2A>，會在變更控制項的任何屬性時呼叫。|
|<xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.ControlDesigner.RaiseResizeEvent%2A>|由於調整大小是由 <xref:System.Web.UI.Design.ControlDesigner.OnComponentChanged%2A?displayProperty=nameWithType> 方法處理，因此不建議使用這個方法。|
|<xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.ControlDesigner.ReadOnly%2A>|建議的替代做法是改從 <xref:System.Web.UI.Design.ContainerControlDesigner?displayProperty=nameWithType> 繼承，並使用 <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=nameWithType>。 區域可讓您進一步控制設計工具中的內容。|
|<xref:System.Web.UI.Design.HtmlControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.HtmlControlDesigner.Behavior%2A>|建議的替代做法是 <xref:System.Web.UI.Design.ControlDesigner.Tag%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Design.HtmlControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.HtmlControlDesigner.DesignTimeElement%2A>|使用這個屬性會產生編譯器錯誤。<br /><br /> 錯誤：無法再參考這個屬性，但已將其加入來支援現有已編譯的應用程式。 設計階段項目不一定可以存取標記中的項目。 <xref:System.Web.UI.Design.WebFormsRootDesigner?displayProperty=nameWithType> 有處理用戶端指令碼和控制項的替代方法。|
|<xref:System.Web.UI.Design.HtmlControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.HtmlControlDesigner.OnBehaviorAttached%2A>|建議的替代做法是 <xref:System.Web.UI.Design.ControlDesigner.Tag%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Design.HtmlControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.HtmlControlDesigner.OnBehaviorDetaching%2A>|建議的替代做法是 <xref:System.Web.UI.Design.ControlDesigner.Tag%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Design.HtmlControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.HtmlControlDesigner.OnBindingsCollectionChanged%2A>|建議的替代做法是處理 [HtmlControlDesigner.DataBindings.Changed](xref:System.Web.UI.DataBindingCollection.Changed) 事件。 <xref:System.Web.UI.Design.HtmlControlDesigner.DataBindings%2A?displayProperty=nameWithType> 屬性所傳回的 <xref:System.Web.UI.DataBindingCollection> 集合可讓您進一步控制與控制項關聯的資料繫結。|
|<xref:System.Web.UI.Design.HtmlControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.HtmlControlDesigner.ShouldCodeSerialize%2A>|由於不支援程式碼序列化，因此不建議使用這個屬性。|
|<xref:System.Web.UI.Design.TemplatedControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.TemplatedControlDesigner.ActiveTemplateEditingFrame%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個屬性。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.TemplatedControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.TemplatedControlDesigner.CreateTemplateEditingFrame%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.TemplatedControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.TemplatedControlDesigner.EnterTemplateMode%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.TemplatedControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.TemplatedControlDesigner.ExitTemplateMode%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.TemplatedControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.TemplatedControlDesigner.GetCachedTemplateEditingVerbs%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.TemplatedControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.TemplatedControlDesigner.GetTemplateContainerDataItemProperty%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.TemplatedControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.TemplatedControlDesigner.GetTemplateContainerDataSource%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.TemplatedControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.TemplatedControlDesigner.GetTemplateContent%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.TemplatedControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.TemplatedControlDesigner.GetTemplateEditingVerbs%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.TemplatedControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.TemplatedControlDesigner.GetTemplatePropertyParentType%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.TemplatedControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.TemplatedControlDesigner.InTemplateMode%2A>|建議的替代做法是 <xref:System.Web.UI.Design.ControlDesigner.InTemplateMode%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Design.TemplatedControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.TemplatedControlDesigner.OnBehaviorAttached%2A>|建議的替代做法是 <xref:System.Web.UI.Design.ControlDesigner.Tag%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Design.TemplatedControlDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.TemplatedControlDesigner.SetTemplateContent%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.WebControls.BaseDataListDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.BaseDataListDesigner.GetTemplateContainerDataSource%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.WebControls.BaseDataListDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.BaseDataListDesigner.OnAutoFormat%2A>|由於 [自動格式設定] 對話方塊是由設計工具主應用程式啟動，因此不建議使用這個方法。 <xref:System.Web.UI.Design.ControlDesigner.AutoFormats%2A?displayProperty=nameWithType> 屬性會公開可用的自動格式設定清單。|
|<xref:System.Web.UI.Design.WebControls.DataGridDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.DataGridDesigner.CreateTemplateEditingFrame%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.WebControls.DataGridDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.DataGridDesigner.GetCachedTemplateEditingVerbs%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.WebControls.DataGridDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.DataGridDesigner.GetTemplateContainerDataItemProperty%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.WebControls.DataGridDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.DataGridDesigner.GetTemplateContent%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.WebControls.DataGridDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.DataGridDesigner.GetTemplatePropertyParentType%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.WebControls.DataGridDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.DataGridDesigner.SetTemplateContent%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.WebControls.DataListDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.DataListDesigner.CreateTemplateEditingFrame%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.WebControls.DataListDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.DataListDesigner.GetCachedTemplateEditingVerbs%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.WebControls.DataListDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.DataListDesigner.GetTemplateContainerDataItemProperty%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.WebControls.DataListDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.DataListDesigner.GetTemplateContent%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.WebControls.DataListDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.DataListDesigner.SetTemplateContent%2A>|由於範本編輯功能是在 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> 中處理，因此不建議使用這個方法。 若要支援範本編輯功能，請公開 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> 屬性中的範本資料，並呼叫 [`ControlDesigner.SetViewFlags(ViewFlags.TemplateEditing, true)`](xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A)。|
|<xref:System.Web.UI.Design.WebControls.PanelDesigner?displayProperty=nameWithType>|<xref:System.Web.UI.Design.WebControls.PanelDesigner.OnBehaviorAttached%2A>|建議的替代做法是 <xref:System.Web.UI.Design.ControlDesigner.Tag%2A?displayProperty=nameWithType>。|
|<xref:System.Windows.Forms.Design.ControlDesigner?displayProperty=nameWithType>|<xref:System.Windows.Forms.Design.ControlDesigner.OnSetComponentDefaults%2A>|這個方法已被取代。 請改用 <xref:System.Windows.Forms.Design.ControlDesigner.InitializeNewComponent%2A?displayProperty=nameWithType> 。|

<a name="system"></a>

### <a name="assembly-systemdll"></a>組件：System.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:Microsoft.CSharp.CSharpCodeProvider?displayProperty=nameWithType>|<xref:Microsoft.CSharp.CSharpCodeProvider.CreateCompiler%2A>|呼叫端不應該使用 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> 介面，而是改為直接在 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 類別上使用方法。|
|<xref:Microsoft.CSharp.CSharpCodeProvider?displayProperty=nameWithType>|<xref:Microsoft.CSharp.CSharpCodeProvider.CreateGenerator%2A>|呼叫端不應該使用 <xref:System.CodeDom.Compiler.ICodeGenerator?displayProperty=nameWithType> 介面，而是改為直接在 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 類別上使用方法。|
|<xref:Microsoft.VisualBasic.VBCodeProvider?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.VBCodeProvider.CreateCompiler%2A>|呼叫端不應該使用 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> 介面，而是改為直接在 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 類別上使用方法。|
|<xref:Microsoft.VisualBasic.VBCodeProvider?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.VBCodeProvider.CreateGenerator%2A>|呼叫端不應該使用 <xref:System.CodeDom.Compiler.ICodeGenerator?displayProperty=nameWithType> 介面，而是改為直接在 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 類別上使用方法。|
|<xref:Microsoft.Win32.SystemEvents?displayProperty=nameWithType>|<xref:Microsoft.Win32.SystemEvents.LowMemory>|這個事件已被取代。|
|<xref:System.Uri?displayProperty=nameWithType>|<xref:System.Uri.Canonicalize%2A>|這個方法已被取代。 系統不會使用這個方法。|
|<xref:System.Uri?displayProperty=nameWithType>|<xref:System.Uri.CheckSecurity%2A>|這個方法已被取代。 系統不會使用這個方法。|
|<xref:System.Uri?displayProperty=nameWithType>|<xref:System.Uri.Escape%2A>|這個方法已被取代。 系統不會使用這個方法。|
|<xref:System.Uri?displayProperty=nameWithType>|<xref:System.Uri.EscapeString%2A>|這個方法已被取代。 請使用 <xref:System.Uri.GetComponents%2A> 方法或靜態 <xref:System.Uri.EscapeUriString%2A> 方法，逸出 URI 元件或字串。|
|<xref:System.Uri?displayProperty=nameWithType>|<xref:System.Uri.IsBadFileSystemCharacter%2A>|這個方法已被取代。 系統不會使用這個方法。|
|<xref:System.Uri?displayProperty=nameWithType>|<xref:System.Uri.IsExcludedCharacter%2A>|這個方法已被取代。 系統不會使用這個方法。|
|<xref:System.Uri?displayProperty=nameWithType>|<xref:System.Uri.IsReservedCharacter%2A>|這個方法已被取代。 系統不會使用這個方法。|
|<xref:System.Uri?displayProperty=nameWithType>|<xref:System.Uri.MakeRelative%2A>|這個方法已被取代。 使用 <xref:System.Uri.MakeRelativeUri%2A?displayProperty=nameWithType>。|
|<xref:System.Uri?displayProperty=nameWithType>|<xref:System.Uri.Parse%2A>|這個方法已被取代。 系統不會使用這個方法。|
|<xref:System.Uri?displayProperty=nameWithType>|<xref:System.Uri.Unescape%2A>|這個方法已被取代。 請使用 <xref:System.Uri.GetComponents%2A?displayProperty=nameWithType> 方法或靜態 <xref:System.Uri.EscapeUriString%2A?displayProperty=nameWithType> 方法，逸出 URI 元件或字串。|
|<xref:System.Uri?displayProperty=nameWithType>|<xref:System.Uri.%23ctor%28System.String%2CSystem.Boolean%29>|這個建構函式已被取代。 使用 <xref:System.Uri.%23ctor%28System.String%29>。 `dontEscape` 參數已被取代，而且一律為 `false`。|
|<xref:System.Uri?displayProperty=nameWithType>|<xref:System.Uri.%23ctor%28System.Uri%2CSystem.String%2CSystem.Boolean%29>|這個建構函式已被取代。 使用 <xref:System.Uri.%23ctor%28System.Uri%2CSystem.String%29>。 `dontEscape` 參數已被取代，而且一律為 `false`。|
|<xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>|<xref:System.CodeDom.Compiler.CodeDomProvider.CreateCompiler%2A>|呼叫端不應該使用 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> 介面，而是改為直接在 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 類別上使用方法。 繼承自 <xref:System.CodeDom.Compiler.CodeDomProvider> 的類型仍必須實作這個介面，而且應該排除這個警告，或是同時淘汰這個方法。|
|<xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>|<xref:System.CodeDom.Compiler.CodeDomProvider.CreateGenerator%2A>|呼叫端不應該使用 <xref:System.CodeDom.Compiler.ICodeGenerator?displayProperty=nameWithType> 介面，而是改為直接在 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 類別上使用方法。 繼承自 <xref:System.CodeDom.Compiler.CodeDomProvider> 的類型仍必須實作這個介面，而且應該排除這個警告，或是同時淘汰這個方法。|
|<xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>|<xref:System.CodeDom.Compiler.CodeDomProvider.CreateParser%2A>|呼叫端不應該使用 <xref:System.CodeDom.Compiler.ICodeParser?displayProperty=nameWithType> 介面，而是改為直接在 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 類別上使用方法。 繼承自 <xref:System.CodeDom.Compiler.CodeDomProvider> 的類型仍必須實作這個介面，而且應該排除這個警告，或是同時淘汰這個方法。|
|<xref:System.CodeDom.Compiler.CompilerParameters?displayProperty=nameWithType>|<xref:System.CodeDom.Compiler.CompilerParameters.Evidence%2A>|CAS 原則已經過時，將在未來的 .NET Framework 版本中移除。 如需詳細資訊，請參閱 [.NET Framework 4 中的安全性變更](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee191568%28v=vs.100%29)。|
|<xref:System.CodeDom.Compiler.CompilerResults?displayProperty=nameWithType>|<xref:System.CodeDom.Compiler.CompilerResults.Evidence%2A>|CAS 原則已經過時，將在未來的 .NET Framework 版本中移除。 如需詳細資訊，請參閱 [.NET Framework 4 中的安全性變更](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee191568%28v=vs.100%29)。|
|<xref:System.Collections.Specialized.NameObjectCollectionBase?displayProperty=nameWithType>|<xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor%28System.Collections.IHashCodeProvider%2CSystem.Collections.IComparer%29>|請改用 <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor%28System.Collections.IEqualityComparer%29> 。|
|<xref:System.Collections.Specialized.NameObjectCollectionBase?displayProperty=nameWithType>|<xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor%28System.Int32%2CSystem.Collections.IHashCodeProvider%2CSystem.Collections.IComparer%29>|請改用 <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor%28System.Int32%2CSystem.Collections.IEqualityComparer%29> 。|
|<xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType>|<xref:System.Collections.Specialized.NameValueCollection.%23ctor%28System.Collections.IHashCodeProvider%2CSystem.Collections.IComparer%29>|請改用 <xref:System.Collections.Specialized.NameValueCollection.%23ctor%28System.Collections.IEqualityComparer%29> 。|
|<xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType>|<xref:System.Collections.Specialized.NameValueCollection.%23ctor%28System.Int32%2CSystem.Collections.IHashCodeProvider%2CSystem.Collections.IComparer%29>|請改用 <xref:System.Collections.Specialized.NameValueCollection.%23ctor%28System.Int32%2CSystem.Collections.IEqualityComparer%29> 。|
|<xref:System.ComponentModel.AsyncCompletedEventArgs?displayProperty=nameWithType>|<xref:System.ComponentModel.AsyncCompletedEventArgs.%23ctor>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.ComponentModel.MemberDescriptor?displayProperty=nameWithType>|<xref:System.ComponentModel.MemberDescriptor.GetInvokee%2A>|這個方法已被取代。 請改用 <xref:System.ComponentModel.MemberDescriptor.GetInvocationTarget%2A?displayProperty=nameWithType> 。|
|<xref:System.ComponentModel.TypeDescriptor?displayProperty=nameWithType>|<xref:System.ComponentModel.TypeDescriptor.ComNativeDescriptorHandler%2A>|這個屬性已被取代。 請改用類型描述提供者來提供 COM 類型的類型資訊。|
|<xref:System.ComponentModel.Design.DesignerTransactionCloseEventArgs?displayProperty=nameWithType>|<xref:System.ComponentModel.Design.DesignerTransactionCloseEventArgs.%23ctor%28System.Boolean%29>|這個建構函式已經過時。 請改用 <xref:System.ComponentModel.Design.DesignerTransactionCloseEventArgs.%23ctor%28System.Boolean%2CSystem.Boolean%29> 。|
|<xref:System.ComponentModel.Design.SelectionTypes?displayProperty=nameWithType>|<xref:System.ComponentModel.Design.SelectionTypes.Click>|這個值已被取代。 請改用 <xref:System.ComponentModel.Design.SelectionTypes.Primary?displayProperty=nameWithType> 。|
|<xref:System.ComponentModel.Design.SelectionTypes?displayProperty=nameWithType>|<xref:System.ComponentModel.Design.SelectionTypes.MouseDown>|這個值已被取代。 它不再受支援。|
|<xref:System.ComponentModel.Design.SelectionTypes?displayProperty=nameWithType>|<xref:System.ComponentModel.Design.SelectionTypes.MouseUp>|這個值已被取代。 它不再受支援。|
|<xref:System.ComponentModel.Design.SelectionTypes?displayProperty=nameWithType>|<xref:System.ComponentModel.Design.SelectionTypes.Normal>|這個值已被取代。 請改用 <xref:System.ComponentModel.Design.SelectionTypes.Auto?displayProperty=nameWithType> 。|
|<xref:System.ComponentModel.Design.SelectionTypes?displayProperty=nameWithType>|<xref:System.ComponentModel.Design.SelectionTypes.Valid>|這個值已被取代。 請使用 <xref:System.Enum?displayProperty=nameWithType> 類別方法來決定有效值，或使用類型轉換子。|
|<xref:System.ComponentModel.Design.ViewTechnology?displayProperty=nameWithType>|<xref:System.ComponentModel.Design.ViewTechnology.Passthrough>|這個值已被取代。 請改用 <xref:System.ComponentModel.Design.ViewTechnology.Default?displayProperty=nameWithType> 。|
|<xref:System.ComponentModel.Design.ViewTechnology?displayProperty=nameWithType>|<xref:System.ComponentModel.Design.ViewTechnology.WindowsForms>|這個值已被取代。 請改用 <xref:System.ComponentModel.Design.ViewTechnology.Default?displayProperty=nameWithType> 。|
|<xref:System.Configuration.ConfigurationException?displayProperty=nameWithType>|<xref:System.Configuration.ConfigurationException.%23ctor>|這個類別已經過時。 若要建立新的例外狀況，請建立 <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType>。|
|<xref:System.Configuration.ConfigurationException?displayProperty=nameWithType>|<xref:System.Configuration.ConfigurationException.%23ctor%28System.String%29>|這個類別已經過時。 若要建立新的例外狀況，請建立 <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType>。|
|<xref:System.Configuration.ConfigurationException?displayProperty=nameWithType>|<xref:System.Configuration.ConfigurationException.%23ctor%28System.String%2CSystem.Exception%29>|這個類別已經過時。 若要建立新的例外狀況，請建立 <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType>。|
|<xref:System.Configuration.ConfigurationException?displayProperty=nameWithType>|<xref:System.Configuration.ConfigurationException.%23ctor%28System.String%2CSystem.Exception%2CSystem.String%2CSystem.Int32%29>|這個類別已經過時。 若要建立新的例外狀況，請建立 <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType>。|
|<xref:System.Configuration.ConfigurationException?displayProperty=nameWithType>|<xref:System.Configuration.ConfigurationException.%23ctor%28System.String%2CSystem.Exception%2CSystem.Xml.XmlNode%29>|這個類別已經過時。 若要建立新的例外狀況，請建立 <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType>。|
|<xref:System.Configuration.ConfigurationException?displayProperty=nameWithType>|<xref:System.Configuration.ConfigurationException.%23ctor%28System.String%2CSystem.String%2CSystem.Int32%29>|這個類別已經過時。 若要建立新的例外狀況，請建立 <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType>。|
|<xref:System.Configuration.ConfigurationException?displayProperty=nameWithType>|<xref:System.Configuration.ConfigurationException.%23ctor%28System.String%2CSystem.Xml.XmlNode%29>|這個類別已經過時。 若要建立新的例外狀況，請建立 <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType>。|
|<xref:System.Configuration.ConfigurationException?displayProperty=nameWithType>|<xref:System.Configuration.ConfigurationException.GetXmlNodeFilename%2A>|這個類別已經過時。 請改用 <xref:System.Configuration.ConfigurationErrorsException.GetFilename%2A?displayProperty=nameWithType> 。|
|<xref:System.Configuration.ConfigurationException?displayProperty=nameWithType>|<xref:System.Configuration.ConfigurationException.GetXmlNodeLineNumber%2A>|這個類別已經過時。 請改用 <xref:System.Configuration.ConfigurationErrorsException.GetLineNumber%28System.Xml.XmlNode%29?displayProperty=nameWithType>。|
|<xref:System.Configuration.ConfigurationSettings?displayProperty=nameWithType>|<xref:System.Configuration.ConfigurationSettings.AppSettings%2A>|這個方法已過時。 這個方法已取代成 <xref:System.Configuration.ConfigurationManager.AppSettings%2A?displayProperty=nameWithType>。|
|<xref:System.Configuration.ConfigurationSettings?displayProperty=nameWithType>|<xref:System.Configuration.ConfigurationSettings.GetConfig%2A>|這個方法已過時。 這個方法已取代成 <xref:System.Configuration.ConfigurationManager.GetSection%2A?displayProperty=nameWithType>。|
|<xref:System.Diagnostics.EventLog?displayProperty=nameWithType>|<xref:System.Diagnostics.EventLog.CreateEventSource%28System.String%2CSystem.String%2CSystem.String%29>|這個方法已被取代。 請改用 <xref:System.Diagnostics.EventLog.CreateEventSource%28System.Diagnostics.EventSourceCreationData%29> 。|
|<xref:System.Diagnostics.EventLogEntry?displayProperty=nameWithType>|<xref:System.Diagnostics.EventLogEntry.EventID%2A>|這個屬性已被取代。 請改用 <xref:System.Diagnostics.EventLogEntry.InstanceId%2A?displayProperty=nameWithType> 。|
|<xref:System.Diagnostics.EventLogPermissionAccess?displayProperty=nameWithType>|<xref:System.Diagnostics.EventLogPermissionAccess.Audit>|這個成員已被取代。 請改用 <xref:System.Diagnostics.EventLogPermissionAccess.Administer?displayProperty=nameWithType> 。|
|<xref:System.Diagnostics.EventLogPermissionAccess?displayProperty=nameWithType>|<xref:System.Diagnostics.EventLogPermissionAccess.Browse>|這個成員已被取代。 請改用 <xref:System.Diagnostics.EventLogPermissionAccess.Administer?displayProperty=nameWithType> 。|
|<xref:System.Diagnostics.EventLogPermissionAccess?displayProperty=nameWithType>|<xref:System.Diagnostics.EventLogPermissionAccess.Instrument>|這個成員已被取代。 請改用 <xref:System.Diagnostics.EventLogPermissionAccess.Write?displayProperty=nameWithType> 。|
|<xref:System.Diagnostics.InstanceDataCollection?displayProperty=nameWithType>|<xref:System.Diagnostics.InstanceDataCollection.%23ctor%2A>|這個建構函式已被取代。 請改用 <xref:System.Diagnostics.InstanceDataCollectionCollection.Item%2A?displayProperty=nameWithType> 來取得這個集合的執行個體。|
|<xref:System.Diagnostics.InstanceDataCollectionCollection?displayProperty=nameWithType>|<xref:System.Diagnostics.InstanceDataCollectionCollection.%23ctor%2A>|這個建構函式已被取代。 請改用 <xref:System.Diagnostics.PerformanceCounterCategory.ReadCategory%2A?displayProperty=nameWithType> 來取得這個集合的執行個體。|
|<xref:System.Diagnostics.PerformanceCounter?displayProperty=nameWithType>|<xref:System.Diagnostics.PerformanceCounter.DefaultFileMappingSize>|這個欄位已被取代，而且不再使用。 請使用 machine.config 或應用程式組態檔來設定 <xref:System.Diagnostics.PerformanceCounter?displayProperty=nameWithType> 檔案對應的大小。|
|<xref:System.Diagnostics.PerformanceCounterCategory?displayProperty=nameWithType>|<xref:System.Diagnostics.PerformanceCounterCategory.Create%28System.String%2CSystem.String%2CSystem.Diagnostics.CounterCreationDataCollection%29>|這個方法已被取代。 請改用 <xref:System.Diagnostics.PerformanceCounterCategory.Create%28System.String%2CSystem.String%2CSystem.Diagnostics.PerformanceCounterCategoryType%2CSystem.Diagnostics.CounterCreationDataCollection%29> 。|
|<xref:System.Diagnostics.PerformanceCounterCategory?displayProperty=nameWithType>|<xref:System.Diagnostics.PerformanceCounterCategory.Create%28System.String%2CSystem.String%2CSystem.String%2CSystem.String%29>|這個方法已被取代。 請改用 <xref:System.Diagnostics.PerformanceCounterCategory.Create%28System.String%2CSystem.String%2CSystem.Diagnostics.PerformanceCounterCategoryType%2CSystem.String%2CSystem.String%29> 。|
|<xref:System.Diagnostics.PerformanceCounterManager?displayProperty=nameWithType>|<xref:System.Diagnostics.PerformanceCounterManager.System%23Diagnostics%23ICollectData%23CloseData%2A>|這個類別已被取代。 請改為透過 <xref:System.Diagnostics.PerformanceCounter> 類別使用效能計數器。|
|<xref:System.Diagnostics.PerformanceCounterManager?displayProperty=nameWithType>|<xref:System.Diagnostics.PerformanceCounterManager.System%23Diagnostics%23ICollectData%23CollectData%2A>|這個類別已被取代。 請改為透過 <xref:System.Diagnostics.PerformanceCounter> 類別使用效能計數器。|
|<xref:System.Diagnostics.PerformanceCounterManager?displayProperty=nameWithType>|<xref:System.Diagnostics.PerformanceCounterManager.%23ctor%2A>|這個類別已被取代。 請改為透過 <xref:System.Diagnostics.PerformanceCounter?displayProperty=nameWithType> 類別使用效能計數器。|
|<xref:System.Diagnostics.PerformanceCounterPermissionAccess?displayProperty=nameWithType>|<xref:System.Diagnostics.PerformanceCounterPermissionAccess.Browse>|這個成員已被取代。 請改用 <xref:System.Diagnostics.PerformanceCounterPermissionAccess.Read?displayProperty=nameWithType> 。|
|<xref:System.Diagnostics.PerformanceCounterPermissionAccess?displayProperty=nameWithType>|<xref:System.Diagnostics.PerformanceCounterPermissionAccess.Instrument>|這個成員已被取代。 請改用 <xref:System.Diagnostics.PerformanceCounterPermissionAccess.Write?displayProperty=nameWithType> 。|
|<xref:System.Diagnostics.Process?displayProperty=nameWithType>|<xref:System.Diagnostics.Process.NonpagedSystemMemorySize%2A>|這個屬性已被取代。 請改用 <xref:System.Diagnostics.Process.NonpagedSystemMemorySize64%2A?displayProperty=nameWithType> 。|
|<xref:System.Diagnostics.Process?displayProperty=nameWithType>|<xref:System.Diagnostics.Process.PagedMemorySize%2A>|這個屬性已被取代。 請改用 <xref:System.Diagnostics.Process.PagedMemorySize64%2A> 。|
|<xref:System.Diagnostics.Process?displayProperty=nameWithType>|<xref:System.Diagnostics.Process.PagedSystemMemorySize%2A>|這個屬性已被取代。 請改用 <xref:System.Diagnostics.Process.PagedSystemMemorySize64%2A?displayProperty=nameWithType> 。|
|<xref:System.Diagnostics.Process?displayProperty=nameWithType>|<xref:System.Diagnostics.Process.PeakPagedMemorySize%2A>|這個屬性已被取代。 請改用 <xref:System.Diagnostics.Process.PeakPagedMemorySize64%2A?displayProperty=nameWithType> 。|
|<xref:System.Diagnostics.Process?displayProperty=nameWithType>|<xref:System.Diagnostics.Process.PeakVirtualMemorySize%2A>|這個屬性已被取代。 請改用 <xref:System.Diagnostics.Process.PeakVirtualMemorySize64%2A?displayProperty=nameWithType> 。|
|<xref:System.Diagnostics.Process?displayProperty=nameWithType>|<xref:System.Diagnostics.Process.PeakWorkingSet%2A>|這個屬性已被取代。 請改用 <xref:System.Diagnostics.Process.PeakWorkingSet64%2A?displayProperty=nameWithType> 。|
|<xref:System.Diagnostics.Process?displayProperty=nameWithType>|<xref:System.Diagnostics.Process.PrivateMemorySize%2A>|這個屬性已被取代。 請改用 <xref:System.Diagnostics.Process.PrivateMemorySize64%2A?displayProperty=nameWithType> 。|
|<xref:System.Diagnostics.Process?displayProperty=nameWithType>|<xref:System.Diagnostics.Process.VirtualMemorySize%2A>|這個屬性已被取代。 請改用 <xref:System.Diagnostics.Process.VirtualMemorySize64%2A?displayProperty=nameWithType> 。|
|<xref:System.Diagnostics.Process?displayProperty=nameWithType>|<xref:System.Diagnostics.Process.WorkingSet%2A>|這個屬性已被取代。 請改用 <xref:System.Diagnostics.Process.WorkingSet64%2A?displayProperty=nameWithType> 。|
|<xref:System.Net.Dns?displayProperty=nameWithType>|<xref:System.Net.Dns.BeginGetHostByName%2A>|<xref:System.Net.Dns.BeginGetHostByName%2A> 對於這個類型而言已過時，請改為使用 <xref:System.Net.Dns.BeginGetHostEntry%28System.String%2CSystem.AsyncCallback%2CSystem.Object%29?displayProperty=nameWithType>。|
|<xref:System.Net.Dns?displayProperty=nameWithType>|<xref:System.Net.Dns.BeginResolve%28System.String%2CSystem.AsyncCallback%2CSystem.Object%29>|<xref:System.Net.Dns.BeginResolve%28System.String%2CSystem.AsyncCallback%2CSystem.Object%29> 對於這個類型而言已過時，請改為使用 <xref:System.Net.Dns.BeginGetHostEntry%28System.String%2CSystem.AsyncCallback%2CSystem.Object%29?displayProperty=nameWithType>。|
|<xref:System.Net.Dns?displayProperty=nameWithType>|<xref:System.Net.Dns.EndGetHostByName%2A>|<xref:System.Net.Dns.EndGetHostByName%2A> 對於這個類型而言已過時，請改為使用 <xref:System.Net.Dns.EndGetHostEntry%2A?displayProperty=nameWithType>。|
|<xref:System.Net.Dns?displayProperty=nameWithType>|<xref:System.Net.Dns.EndResolve%2A>|<xref:System.Net.Dns.EndResolve%2A> 對於這個類型而言已過時，請改為使用 <xref:System.Net.Dns.EndGetHostEntry%2A?displayProperty=nameWithType>。|
|<xref:System.Net.Dns?displayProperty=nameWithType>|<xref:System.Net.Dns.GetHostByAddress%28System.Net.IPAddress%29>|<xref:System.Net.Dns.GetHostByAddress%28System.Net.IPAddress%29> 對於這個類型而言已過時，請改為使用 <xref:System.Net.Dns.GetHostEntry%28System.Net.IPAddress%29?displayProperty=nameWithType>。|
|<xref:System.Net.Dns?displayProperty=nameWithType>|<xref:System.Net.Dns.GetHostByAddress%28System.String%29>|<xref:System.Net.Dns.GetHostByAddress%28System.String%29> 對於這個類型而言已過時，請改為使用 <xref:System.Net.Dns.GetHostEntry%28System.String%29?displayProperty=nameWithType>。|
|<xref:System.Net.Dns?displayProperty=nameWithType>|<xref:System.Net.Dns.GetHostByName%2A>|<xref:System.Net.Dns.GetHostByName%2A> 對於這個類型而言已過時，請改為使用 <xref:System.Net.Dns.GetHostEntry%28System.String%29?displayProperty=nameWithType>。|
|<xref:System.Net.Dns?displayProperty=nameWithType>|<xref:System.Net.Dns.Resolve%2A>|<xref:System.Net.Dns.Resolve%2A> 對於這個類型而言已過時，請改為使用 <xref:System.Net.Dns.GetHostEntry%28System.String%29?displayProperty=nameWithType>。|
|<xref:System.Net.FileWebRequest?displayProperty=nameWithType>|<xref:System.Net.FileWebRequest.%23ctor%2A>|序列化對於這個類型而言已經過時。|
|<xref:System.Net.FileWebResponse?displayProperty=nameWithType>|<xref:System.Net.FileWebResponse.%23ctor%2A>|序列化對於這個類型而言已經過時。|
|<xref:System.Net.HttpWebRequest?displayProperty=nameWithType>|<xref:System.Net.HttpWebRequest.%23ctor>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Net.HttpWebRequest?displayProperty=nameWithType>|<xref:System.Net.HttpWebRequest.%23ctor%28System.Runtime.Serialization.SerializationInfo%2CSystem.Runtime.Serialization.StreamingContext%29>|序列化對於這個類型而言已經過時。|
|<xref:System.Net.HttpWebResponse?displayProperty=nameWithType>|<xref:System.Net.HttpWebResponse.%23ctor>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Net.HttpWebResponse?displayProperty=nameWithType>|<xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)>|序列化對於這個類型而言已經過時。|
|<xref:System.Net.IPAddress?displayProperty=nameWithType>|<xref:System.Net.IPAddress.Address%2A>|這個屬性已被取代。 它會相依於位址系列。 請改用 <xref:System.Net.IPAddress.Equals%2A?displayProperty=nameWithType> 方法來執行比較。|
|<xref:System.Net.ServicePointManager?displayProperty=nameWithType>|<xref:System.Net.ServicePointManager.CertificatePolicy%2A>|<xref:System.Net.ServicePointManager.CertificatePolicy%2A> 對於這個類型而言已經過時。 請改用 <xref:System.Net.ServicePointManager.ServerCertificateValidationCallback%2A?displayProperty=nameWithType> 。|
|<xref:System.Net.WebClient?displayProperty=nameWithType>|<xref:System.Net.WebClient.AllowReadStreamBuffering%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Net.WebClient?displayProperty=nameWithType>|<xref:System.Net.WebClient.AllowWriteStreamBuffering%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Net.WebClient?displayProperty=nameWithType>|<xref:System.Net.WebClient.OnWriteStreamClosed%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Net.WebClient?displayProperty=nameWithType>|<xref:System.Net.WebClient.WriteStreamClosed>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Net.WebProxy?displayProperty=nameWithType>|<xref:System.Net.WebProxy.GetDefaultProxy%2A>|這個方法已被取代。 請使用預設為您選取的 Proxy。|
|<xref:System.Net.WebRequest?displayProperty=nameWithType>|<xref:System.Net.WebRequest.CreatorInstance%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Net.WebRequest?displayProperty=nameWithType>|<xref:System.Net.WebRequest.RegisterPortableWebRequestCreator%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Net.WriteStreamClosedEventArgs?displayProperty=nameWithType>|<xref:System.Net.WriteStreamClosedEventArgs.Error%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Net.WriteStreamClosedEventArgs?displayProperty=nameWithType>|<xref:System.Net.WriteStreamClosedEventArgs.%23ctor%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Net.Mail.MailMessage?displayProperty=nameWithType>|<xref:System.Net.Mail.MailMessage.ReplyTo%2A>|<xref:System.Net.Mail.MailMessage.ReplyTo%2A> 對於這個類型而言已經過時。 請改用可接受多個位址的 <xref:System.Net.Mail.MailMessage.ReplyToList%2A?displayProperty=nameWithType>。|
|<xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType>|<xref:System.Net.NetworkInformation.NetworkChange.%23ctor>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType>|<xref:System.Net.NetworkInformation.NetworkChange.RegisterNetworkChange%28System.Net.NetworkInformation.NetworkChange%29>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Net.Sockets.Socket?displayProperty=nameWithType>|<xref:System.Net.Sockets.Socket.SupportsIPv4%2A>|<xref:System.Net.Sockets.Socket.SupportsIPv4%2A> 對於這個類型而言已經過時。 請改用 <xref:System.Net.Sockets.Socket.OSSupportsIPv4%2A?displayProperty=nameWithType> 。|
|<xref:System.Net.Sockets.Socket?displayProperty=nameWithType>|<xref:System.Net.Sockets.Socket.SupportsIPv6%2A>|<xref:System.Net.Sockets.Socket.SupportsIPv6%2A> 對於這個類型而言已經過時。 請改用 <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType> 。|
|<xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=nameWithType>|<xref:System.Net.Sockets.SocketAsyncEventArgs.SocketClientAccessPolicyProtocol>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Net.Sockets.TcpListener?displayProperty=nameWithType>|<xref:System.Net.Sockets.TcpListener.%23ctor%28System.Int32%29>|這個方法已被取代。 請改用 <xref:System.Net.Sockets.TcpListener.%23ctor%28System.Net.IPAddress%2CSystem.Int32%29> 。|
|<xref:System.Net.WebSockets.WebSocket?displayProperty=nameWithType>|<xref:System.Net.WebSockets.WebSocket.IsApplicationTargeting45%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 這個成員僅供內部使用，將在未來的 .NET Framework 版本中移除。 請勿呼叫它。|
|<xref:System.Security.Claims.DynamicRoleClaimProvider?displayProperty=nameWithType>|<xref:System.Security.Claims.DynamicRoleClaimProvider.AddDynamicRoleClaims%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 請使用 <xref:System.Security.Claims.ClaimsAuthenticationManager?displayProperty=nameWithType> 將宣告加入 <xref:System.Security.Claims.ClaimsIdentity>。|

<a name="drawing"></a>

### <a name="assembly-systemdrawingdll"></a>組件：System.Drawing.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Drawing.FontFamily?displayProperty=nameWithType>|<xref:System.Drawing.FontFamily.GetFamilies%2A>|請勿使用 <xref:System.Drawing.FontFamily.GetFamilies%2A> 方法，改為使用 <xref:System.Drawing.FontFamily.Families%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.Drawing.Imaging.EncoderParameter?displayProperty=nameWithType>|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 這個建構函式已被取代。 使用 <xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Drawing.Imaging.EncoderParameterValueType%2CSystem.IntPtr%29>。|

<a name="messaging"></a>

### <a name="assembly-systemmessagingdll"></a>組件：System.Messaging.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Messaging.MessageQueue?displayProperty=nameWithType>|<xref:System.Messaging.MessageQueue.GetEnumerator%2A>|這個方法會傳回不正確實作 <xref:System.Messaging.MessageEnumerator.RemoveCurrent%2A?displayProperty=nameWithType> 系列方法的 <xref:System.Messaging.MessageEnumerator?displayProperty=nameWithType>。 請改用 <xref:System.Messaging.MessageQueue.GetMessageEnumerator2%2A?displayProperty=nameWithType> 。|
|<xref:System.Messaging.MessageQueue?displayProperty=nameWithType>|<xref:System.Messaging.MessageQueue.GetMessageEnumerator%2A>|這個方法會傳回不正確實作 <xref:System.Messaging.MessageEnumerator.RemoveCurrent%2A?displayProperty=nameWithType> 系列方法的 <xref:System.Messaging.MessageEnumerator?displayProperty=nameWithType>。 請改用 <xref:System.Messaging.MessageQueue.GetMessageEnumerator2%2A?displayProperty=nameWithType> 。|

<a name="servicemodel"></a>

### <a name="assembly-systemservicemodeldll"></a>組件：System.ServiceModel.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>|<xref:System.ServiceModel.BasicHttpBinding.EnableHttpCookieContainer%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 這個屬性已經過時。 若要啟用 HTTP <xref:System.Net.CookieContainer>，請改用 <xref:System.ServiceModel.HttpBindingBase.AllowCookies%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>|<xref:System.ServiceModel.Configuration.BindingsSection.NetPeerTcpBinding%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 對等通道功能已經過時，未來將會移除。|
|<xref:System.ServiceModel.Dispatcher.ClientOperationCompatBase?displayProperty=nameWithType>|<xref:System.ServiceModel.Dispatcher.ClientOperationCompatBase.ParameterInspectors%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個型別會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.ServiceModel.Dispatcher.ClientRuntimeCompatBase?displayProperty=nameWithType>|<xref:System.ServiceModel.Dispatcher.ClientRuntimeCompatBase.MessageInspectors%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個型別會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.ServiceModel.Dispatcher.ClientRuntimeCompatBase?displayProperty=nameWithType>|<xref:System.ServiceModel.Dispatcher.ClientRuntimeCompatBase.Operations%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個型別會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>|<xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A>|這個屬性已被取代，僅針對回溯相容性而保留。 本機電腦原則將用來判斷是否應該使用 NTLM。|

<a name="smDisc"></a>

### <a name="assembly-systemservicemodeldiscoverydll"></a>組件：System.ServiceModel.Discovery.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint?displayProperty=nameWithType>|<xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint.TransportSettings%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint.TransportSettings%2A> 屬性已經過時。 請考慮使用 <xref:System.ServiceModel.Channels.UdpTransportBindingElement?displayProperty=nameWithType> 來設定傳輸屬性。|
|<xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint?displayProperty=nameWithType>|<xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.TransportSettings%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.TransportSettings%2A> 屬性已經過時。 請考慮使用 <xref:System.ServiceModel.Channels.UdpTransportBindingElement?displayProperty=nameWithType> 來設定傳輸屬性。|

<a name="datavisualization"></a>

### <a name="assembly-systemwebdatavisualizationdll"></a>組件：System.Web.DataVisualization.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Web.UI.DataVisualization.Charting.Chart?displayProperty=nameWithType>|<xref:System.Web.UI.DataVisualization.Charting.Chart.ViewStateData%2A>|<xref:System.Web.UI.DataVisualization.Charting.Chart.ViewStateData%2A> 已被取代。 請改為查看 <xref:System.Web.UI.Control.ViewState%2A?displayProperty=nameWithType>。|

<a name="web"></a>

### <a name="assembly-systemwebdll"></a>組件：System.Web.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Web.HttpContext?displayProperty=nameWithType>|<xref:System.Web.HttpContext.GetAppConfig%2A>|建議的替代做法是 System.Web.dll 中的 <xref:System.Web.Configuration.WebConfigurationManager.GetWebApplicationSection%2A?displayProperty=nameWithType>。|
|<xref:System.Web.HttpContext?displayProperty=nameWithType>|<xref:System.Web.HttpContext.GetConfig%2A>|建議的替代做法是 System.Web.dll 中的 <xref:System.Web.HttpContext.GetSection%2A?displayProperty=nameWithType>。|
|<xref:System.Web.HttpUtility?displayProperty=nameWithType>|<xref:System.Web.HttpUtility.UrlEncodeUnicode%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 這個方法會產生非標準相容的輸出，而且會出現互通性問題。 慣用的替代做法是 <xref:System.Web.HttpUtility.UrlEncode%28System.String%29>。|
|<xref:System.Web.HttpUtility?displayProperty=nameWithType>|<xref:System.Web.HttpUtility.UrlEncodeUnicodeToBytes%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 這個方法會產生非標準相容的輸出，而且會出現互通性問題。 慣用的替代做法是 <xref:System.Web.HttpUtility.UrlEncodeToBytes%28System.String%29>。|
|<xref:System.Web.Configuration.AuthenticationMode?displayProperty=nameWithType>|<xref:System.Web.Configuration.AuthenticationMode.Passport>|這個欄位已經過時。 已不再支援 Passport 驗證產品，並且以 [Microsoft 帳戶](https://go.microsoft.com/fwlink/?LinkId=733413)取代該產品。|
|<xref:System.Web.Configuration.AuthenticationSection?displayProperty=nameWithType>|<xref:System.Web.Configuration.AuthenticationSection.Passport%2A>|這個屬性已經過時。 已不再支援 Passport 驗證產品，並且以 [Microsoft 帳戶](https://go.microsoft.com/fwlink/?LinkId=733413)取代該產品。|
|<xref:System.Web.Configuration.HttpCapabilitiesBase?displayProperty=nameWithType>|<xref:System.Web.Configuration.HttpCapabilitiesBase.JavaScript%2A>|建議的替代做法是 <xref:System.Web.Configuration.HttpCapabilitiesBase.EcmaScriptVersion%2A?displayProperty=nameWithType> 屬性。 <xref:System.Version.Major%2A?displayProperty=nameWithType> 版本值大於或等於 1，表示支援 JavaScript。|
|<xref:System.Web.Configuration.SystemWebSectionGroup?displayProperty=nameWithType>|<xref:System.Web.Configuration.SystemWebSectionGroup.MobileControls%2A>|System.Web.Mobile.dll 已經過時。|
|<xref:System.Web.Routing.UrlRoutingModule?displayProperty=nameWithType>|<xref:System.Web.Routing.UrlRoutingModule.PostMapRequestHandler%2A>|這個方法已過時。 請覆寫 <xref:System.Web.Routing.UrlRoutingModule.Init%2A> 方法以使用 <xref:System.Web.Routing.UrlRoutingModule.PostMapRequestHandler%2A> 事件。|
|<xref:System.Web.Security.FormsAuthentication?displayProperty=nameWithType>|<xref:System.Web.Security.FormsAuthentication.Authenticate%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 建議的替代做法是使用 <xref:System.Web.Security.Membership?displayProperty=nameWithType> API，例如 <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType>。|
|<xref:System.Web.Security.FormsAuthentication?displayProperty=nameWithType>|<xref:System.Web.Security.FormsAuthentication.HashPasswordForStoringInConfigFile%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 建議的替代做法是使用 <xref:System.Web.Security.Membership?displayProperty=nameWithType> API，例如 <xref:System.Web.Security.Membership.CreateUser%2A?displayProperty=nameWithType>。|
|<xref:System.Web.Security.MachineKey?displayProperty=nameWithType>|<xref:System.Web.Security.MachineKey.Decode%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 這個方法已經過時，僅針對現有程式碼的相容性而提供。 建議新的程式碼改用 <xref:System.Web.Security.MachineKey.Protect%2A> 和 <xref:System.Web.Security.MachineKey.Unprotect%2A> 方法。|
|<xref:System.Web.Security.MachineKey?displayProperty=nameWithType>|<xref:System.Web.Security.MachineKey.Encode%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 這個方法已經過時，僅針對現有程式碼的相容性而提供。 建議新的程式碼改用 <xref:System.Web.Security.MachineKey.Protect%2A> 和 <xref:System.Web.Security.MachineKey.Unprotect%2A> 方法。|
|<xref:System.Web.UI.Page?displayProperty=nameWithType>|<xref:System.Web.UI.Page.FileDependencies%2A>|建議的替代做法是 <xref:System.Web.HttpResponse.AddFileDependencies%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Page?displayProperty=nameWithType>|<xref:System.Web.UI.Page.GetPostBackClientEvent%2A>|建議的替代做法是 <xref:System.Web.UI.ClientScriptManager.GetPostBackEventReference%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Page?displayProperty=nameWithType>|<xref:System.Web.UI.Page.GetPostBackClientHyperlink%2A>|建議的替代做法是 <xref:System.Web.UI.ClientScriptManager.GetPostBackClientHyperlink%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Page?displayProperty=nameWithType>|<xref:System.Web.UI.Page.GetPostBackEventReference%28System.Web.UI.Control%29>|建議的替代做法是 <xref:System.Web.UI.ClientScriptManager.GetPostBackEventReference%28System.Web.UI.Control%2CSystem.String%29?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Page?displayProperty=nameWithType>|<xref:System.Web.UI.Page.GetPostBackEventReference%28System.Web.UI.Control%2CSystem.String%29>|建議的替代做法是 <xref:System.Web.UI.ClientScriptManager.GetPostBackEventReference%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Page?displayProperty=nameWithType>|<xref:System.Web.UI.Page.IsClientScriptBlockRegistered%2A>|建議的替代做法是 <xref:System.Web.UI.ClientScriptManager.IsClientScriptBlockRegistered%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Page?displayProperty=nameWithType>|<xref:System.Web.UI.Page.IsStartupScriptRegistered%2A>|建議的替代做法是 <xref:System.Web.UI.ClientScriptManager.IsStartupScriptRegistered%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Page?displayProperty=nameWithType>|<xref:System.Web.UI.Page.RegisterArrayDeclaration%2A>|建議的替代做法是 <xref:System.Web.UI.ClientScriptManager.RegisterArrayDeclaration%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Page?displayProperty=nameWithType>|<xref:System.Web.UI.Page.RegisterClientScriptBlock%2A>|建議的替代做法是 <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Page?displayProperty=nameWithType>|<xref:System.Web.UI.Page.RegisterHiddenField%2A>|建議的替代做法是 <xref:System.Web.UI.ClientScriptManager.RegisterHiddenField%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Page?displayProperty=nameWithType>|<xref:System.Web.UI.Page.RegisterOnSubmitStatement%2A>|建議的替代做法是 <xref:System.Web.UI.ClientScriptManager.RegisterOnSubmitStatement%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Page?displayProperty=nameWithType>|<xref:System.Web.UI.Page.RegisterStartupScript%2A>|建議的替代做法是 <xref:System.Web.UI.ClientScriptManager.RegisterStartupScript%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.Page?displayProperty=nameWithType>|<xref:System.Web.UI.Page.SmartNavigation%2A>|建議的替代方案是 <xref:System.Web.UI.Page.SetFocus%2A?displayProperty=nameWithType> 和 <xref:System.Web.UI.Page.MaintainScrollPositionOnPostBack%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.TemplateControl?displayProperty=nameWithType>|<xref:System.Web.UI.TemplateControl.AutoHandlers%2A>|由於這個屬性已不再可用，因此不建議使用。|
|<xref:System.Web.UI.WebControls.GridView?displayProperty=nameWithType>|<xref:System.Web.UI.WebControls.GridView.CreateAutoGeneratedColumn%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 這個方法是針對回溯相容性而保留。 這個 API 已不再使用。|
|<xref:System.Web.UI.WebControls.Xml?displayProperty=nameWithType>|<xref:System.Web.UI.WebControls.Xml.Document%2A>|建議的替代做法是 <xref:System.Web.UI.WebControls.Xml.XPathNavigator%2A?displayProperty=nameWithType> 屬性。 請建立 <xref:System.Xml.XPath.XPathDocument?displayProperty=nameWithType> 並呼叫 <xref:System.Xml.XPath.XPathDocument.CreateNavigator%2A?displayProperty=nameWithType> 來建立 <xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>。|

<a name="dynamicdata"></a>

### <a name="assembly-systemwebdynamicdatadll"></a>組件：System.Web.DynamicData.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Web.DynamicData.DynamicDataExtensions?displayProperty=nameWithType>|<xref:System.Web.DynamicData.DynamicDataExtensions.EnablePersistedSelection%2A>|請使用資料繫結控制項 (例如 <xref:System.Web.UI.WebControls.GridView?displayProperty=nameWithType> 或 <xref:System.Web.UI.WebControls.ListView?displayProperty=nameWithType>) 上的 `EnablePersistedSelection` 屬性。|

<a name="extensions"></a>

### <a name="assembly-systemwebextensionsdll"></a>組件：System.Web.Extensions.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Web.UI.CompositeScriptReference?displayProperty=nameWithType>|<xref:System.Web.UI.CompositeScriptReference.IsFromSystemWebExtensions%2A>|使用 <xref:System.Web.UI.CompositeScriptReference.IsAjaxFrameworkScript%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.ScriptManager?displayProperty=nameWithType>|<xref:System.Web.UI.ScriptManager.ScriptPath%2A>|這個屬性已經過時。 請改為設定每個個別 <xref:System.Web.UI.ScriptReference?displayProperty=nameWithType> 的 [`System.Web.UI.ScriptReference.Path`](xref:System.Web.UI.ScriptReferenceBase.Path%2A) 屬性。|
|<xref:System.Web.UI.ScriptReference?displayProperty=nameWithType>|<xref:System.Web.UI.ScriptReference.IgnoreScriptPath%2A>|這個屬性已經過時。 請改為設定每個個別 <xref:System.Web.UI.ScriptReference?displayProperty=nameWithType> 的 [`System.Web.UI.ScriptReference.Path`](xref:System.Web.UI.ScriptReferenceBase.Path%2A) 屬性，而不是使用 <xref:System.Web.UI.ScriptManager.ScriptPath%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.ScriptReference?displayProperty=nameWithType>|<xref:System.Web.UI.ScriptReference.IsFromSystemWebExtensions%2A>|使用 <xref:System.Web.UI.ScriptReference.IsAjaxFrameworkScript%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.ScriptReferenceBase?displayProperty=nameWithType>|<xref:System.Web.UI.ScriptReferenceBase.IsFromSystemWebExtensions%2A>|使用 <xref:System.Web.UI.ScriptReferenceBase.IsAjaxFrameworkScript%2A?displayProperty=nameWithType>。|
|<xref:System.Web.UI.ScriptReferenceBase?displayProperty=nameWithType>|<xref:System.Web.UI.ScriptReferenceBase.NotifyScriptLoaded%2A>|指令碼參考已不再需要 <xref:System.Web.UI.ScriptReferenceBase.NotifyScriptLoaded%2A>。|
|<xref:System.Web.UI.ScriptResourceAttribute?displayProperty=nameWithType>|<xref:System.Web.UI.ScriptResourceAttribute.ScriptResourceName%2A>|這個屬性已經過時。 請改用 <xref:System.Web.UI.ScriptResourceAttribute.StringResourceName%2A?displayProperty=nameWithType> 。|
|<xref:System.Web.UI.ScriptResourceAttribute?displayProperty=nameWithType>|<xref:System.Web.UI.ScriptResourceAttribute.TypeName%2A>|這個屬性已經過時。 請改用 <xref:System.Web.UI.ScriptResourceAttribute.StringResourceClientTypeName%2A?displayProperty=nameWithType> 。|

<a name="services"></a>

### <a name="assembly-systemwebservicesdll"></a>組件：System.Web.Services.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Web.Services.Discovery.DiscoveryClientProtocol?displayProperty=nameWithType>|<xref:System.Web.Services.Discovery.DiscoveryClientProtocol.LoadExternals%2A>|這個方法將從未來的版本中移除。 資源探索已不再需要這個方法呼叫。|
|<xref:System.Web.Services.Protocols.SoapHeaderAttribute?displayProperty=nameWithType>|<xref:System.Web.Services.Protocols.SoapHeaderAttribute.Required%2A>|這個屬性將從未來的版本中移除。 不再強制要求 SOAP 訊息中一定要有特定標頭。|

<a name="forms"></a>

### <a name="assembly-systemwindowsformsdll"></a>組件：System.Windows.Forms.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Windows.Forms.AccessibleStates?displayProperty=nameWithType>|<xref:System.Windows.Forms.AccessibleStates.Valid>|這個列舉值已被取代。 沒有任何取代。|
|<xref:System.Windows.Forms.ComboBox?displayProperty=nameWithType>|<xref:System.Windows.Forms.ComboBox.AddItemsCore%2A>|這個方法已被取代。 沒有任何取代。|
|<xref:System.Windows.Forms.Control?displayProperty=nameWithType>|<xref:System.Windows.Forms.Control.RenderRightToLeft%2A>|這個屬性已被取代。 請改用 <xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=nameWithType> 。|
|<xref:System.Windows.Forms.Control?displayProperty=nameWithType>|<xref:System.Windows.Forms.Control.Scale%28System.Single%29>|這個方法已被取代。 請改用 <xref:System.Windows.Forms.Control.Scale%28System.Drawing.SizeF%29?displayProperty=nameWithType> 方法。|
|<xref:System.Windows.Forms.Control?displayProperty=nameWithType>|<xref:System.Windows.Forms.Control.Scale%28System.Single%2CSystem.Single%29>|這個方法已被取代。 請改用 <xref:System.Windows.Forms.Control.Scale%28System.Drawing.SizeF%29?displayProperty=nameWithType> 方法。|
|<xref:System.Windows.Forms.Form?displayProperty=nameWithType>|<xref:System.Windows.Forms.Form.ApplyAutoScaling%2A>|這個方法已被取代。 請改用 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> 方法。|
|<xref:System.Windows.Forms.Form?displayProperty=nameWithType>|<xref:System.Windows.Forms.Form.AutoScale%2A>|這個屬性已被取代。 請改用 <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.Windows.Forms.Form?displayProperty=nameWithType>|<xref:System.Windows.Forms.Form.GetAutoScaleSize%2A>|這個方法已被取代。 請改用 <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.Windows.Forms.Label?displayProperty=nameWithType>|<xref:System.Windows.Forms.Label.RenderTransparent%2A>|這個屬性已被取代。 請改用 <xref:System.Windows.Forms.Control.BackColor%2A> 。|
|<xref:System.Windows.Forms.ListBox?displayProperty=nameWithType>|<xref:System.Windows.Forms.ListBox.AddItemsCore%2A>|這個方法已被取代。 沒有任何取代。|
|<xref:System.Windows.Forms.PrintPreviewDialog?displayProperty=nameWithType>|<xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A>|這個屬性已被取代。 請改用 <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A?displayProperty=nameWithType> 屬性。|

<a name="xaml"></a>

### <a name="assembly-systemxamldll"></a>組件：System.Xaml.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute?displayProperty=nameWithType>|<xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute.ExpressionType%2A>|XAML 剖析器已不使用這個項目。 請參閱<xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute?displayProperty=nameWithType>.|
|<xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute?displayProperty=nameWithType>|<xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute.%23ctor%28System.Type%2CSystem.Type%29>|XAML 剖析器不再使用 `expressionType` 引數。 若要指定預期的傳回類型，請使用 <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute.%23ctor%28System.Type%29?displayProperty=nameWithType>。 若要指定運算式類型的自訂處理方式，請使用 <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute?displayProperty=nameWithType>。|

<a name="xml"></a>

### <a name="assembly-systemxmldll"></a>組件：System.Xml.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Xml.ValidationType?displayProperty=nameWithType>|<xref:System.Xml.ValidationType.Auto>|驗證類型應該指定為 <xref:System.Xml.ValidationType.DTD?displayProperty=nameWithType> 或 <xref:System.Xml.ValidationType.Schema?displayProperty=nameWithType>。|
|<xref:System.Xml.ValidationType?displayProperty=nameWithType>|<xref:System.Xml.ValidationType.XDR>|透過 <xref:System.Xml.XmlValidatingReader?displayProperty=nameWithType> 進行 XDR 驗證已經過時。|
|<xref:System.Xml.XmlConvert?displayProperty=nameWithType>|<xref:System.Xml.XmlConvert.ToDateTime%28System.String%29>|使用 <xref:System.Xml.XmlConvert.ToDateTime%28System.String%2CSystem.Xml.XmlDateTimeSerializationMode%29?displayProperty=nameWithType>。|
|<xref:System.Xml.XmlConvert?displayProperty=nameWithType>|<xref:System.Xml.XmlConvert.ToString%28System.DateTime%29>|使用 <xref:System.Xml.XmlConvert.ToString%28System.DateTime%2CSystem.Xml.XmlDateTimeSerializationMode%29?displayProperty=nameWithType>。|
|<xref:System.Xml.XmlReaderSettings?displayProperty=nameWithType>|<xref:System.Xml.XmlReaderSettings.ProhibitDtd%2A>|請改用 <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.Xml.XmlReaderSettings?displayProperty=nameWithType>|<xref:System.Xml.XmlReaderSettings.%23ctor%28System.Xml.XmlResolver%29>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 此 API 支援 .NET Framework 基礎結構，但不能直接從程式碼使用它。|
|<xref:System.Xml.XmlTextReader?displayProperty=nameWithType>|<xref:System.Xml.XmlTextReader.ProhibitDtd%2A>|請改用 <xref:System.Xml.XmlTextReader.DtdProcessing%2A?displayProperty=nameWithType> 屬性。|
|<xref:System.Xml.Schema.XmlSchema?displayProperty=nameWithType>|<xref:System.Xml.Schema.XmlSchema.Compile%28System.Xml.Schema.ValidationEventHandler%29>|請使用 <xref:System.Xml.Schema.XmlSchemaSet> 進行結構描述編譯和驗證。|
|<xref:System.Xml.Schema.XmlSchema?displayProperty=nameWithType>|<xref:System.Xml.Schema.XmlSchema.Compile%28System.Xml.Schema.ValidationEventHandler%2CSystem.Xml.XmlResolver%29>|請使用 <xref:System.Xml.Schema.XmlSchemaSet> 進行結構描述編譯和驗證。|
|<xref:System.Xml.Schema.XmlSchemaAttribute?displayProperty=nameWithType>|<xref:System.Xml.Schema.XmlSchemaAttribute.AttributeType%2A>|這個屬性已被取代。 請使用 <xref:System.Xml.Schema.XmlSchemaAttribute.AttributeSchemaType%2A?displayProperty=nameWithType> 屬性，這個屬性會傳回強類型的屬性類型。|
|<xref:System.Xml.Schema.XmlSchemaElement?displayProperty=nameWithType>|<xref:System.Xml.Schema.XmlSchemaElement.ElementType%2A>|這個屬性已被取代。 請使用 <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A?displayProperty=nameWithType> 屬性，這個屬性會傳回強類型的項目類型。|
|<xref:System.Xml.Schema.XmlSchemaType?displayProperty=nameWithType>|<xref:System.Xml.Schema.XmlSchemaType.BaseSchemaType%2A>|這個屬性已被取代。 請使用 <xref:System.Xml.Schema.XmlSchemaType.BaseXmlSchemaType%2A?displayProperty=nameWithType> 屬性，這個屬性會傳回強類型的基底結構描述類型。|
|<xref:System.Xml.Serialization.CodeIdentifier?displayProperty=nameWithType>|<xref:System.Xml.Serialization.CodeIdentifier.%23ctor%2A>|這個類別永遠不應該加以建構，因為它僅包含靜態方法。|
|<xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>|<xref:System.Xml.Serialization.XmlSerializer.FromMappings%28System.Xml.Serialization.XmlMapping%5B%5D%2CSystem.Security.Policy.Evidence%29>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.Xml.Serialization.XmlSerializer.FromMappings%2A?displayProperty=nameWithType> 多載。|
|<xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>|<xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%2CSystem.String%2CSystem.Security.Policy.Evidence%29>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.Xml.Serialization.XmlSerializer.%23ctor%2A?displayProperty=nameWithType> 建構函式多載。|
|<xref:System.Xml.Serialization.XmlSerializerFactory?displayProperty=nameWithType>|<xref:System.Xml.Serialization.XmlSerializerFactory.CreateSerializer%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%2CSystem.String%2CSystem.Security.Policy.Evidence%29>|這個方法已經過時，將在未來的 .NET Framework 版本中移除。 請使用未採用 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 參數的 <xref:System.Xml.Serialization.XmlSerializerFactory.CreateSerializer%2A?displayProperty=nameWithType> 多載。|

<a name="MicrosoftMembers"></a>

## <a name="obsolete-members-in-microsoft-assemblies"></a>Microsoft 組件中過時的成員

下表列出 Microsoft 組件中過時的成員。 這些是特殊用途的組件，包含以個別語言 (例如 Microsoft.VisualBasic.dll) 或建置系統 (例如 Microsoft.Build.Engine.dll) 為目標的組件。

<a name="IEHost"></a>

### <a name="assembly-iehostdll-and-ieexecexe"></a>組件：IEHost.dll 和 IEExec.exe

IEHost.dll 和 IEExec.exe 組件已經從 .NET Framework 中移除。 其所有類型和成員都已淘汰，且在 .NET Framework 4.5 中不再支援。 這些組件之前是用來裝載 Windows Form 控制項以及在 Internet Explorer 中執行可執行檔。 這項技術的替代做法包括 ClickOnce、XAML 瀏覽器應用程式 (XBAP) 和 Microsoft Silverlight。

<a name="isymwrapper"></a>

### <a name="assembly-isymwrapperdll"></a>組件：ISymWrapper.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:System.Diagnostics.SymbolStore.SymBinder?displayProperty=nameWithType>|<xref:System.Diagnostics.SymbolStore.SymBinder.GetReader%28System.Int32%2CSystem.String%2CSystem.String%29>|建議的替代做法是 <xref:System.Diagnostics.SymbolStore.SymBinder.GetReader%28System.IntPtr%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType>。 <xref:System.Diagnostics.SymbolStore.ISymbolBinder1.GetReader%2A?displayProperty=nameWithType> 會接受匯入工具介面指標當做 <xref:System.IntPtr?displayProperty=nameWithType> 而不是 <xref:System.Int32?displayProperty=nameWithType>，因此可同時在 32 位元和 64 位元架構上運作。|

<a name="conversion"></a>

### <a name="assembly-microsoftbuildconversionv40dll"></a>組件：Microsoft.Build.Conversion.v4.0.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:Microsoft.Build.Conversion.ProjectFileConverter?displayProperty=nameWithType>|<xref:Microsoft.Build.Conversion.ProjectFileConverter.Convert%28Microsoft.Build.BuildEngine.ProjectLoadSettings%29>|請改用無參數的 <xref:Microsoft.Build.Conversion.ProjectFileConverter.Convert> 多載。|
|<xref:Microsoft.Build.Conversion.ProjectFileConverter?displayProperty=nameWithType>|<xref:Microsoft.Build.Conversion.ProjectFileConverter.Convert%28System.String%29>|請改用無參數的 <xref:Microsoft.Build.Conversion.ProjectFileConverter.Convert> 多載。|
|<xref:Microsoft.Build.Conversion.ProjectFileConverter?displayProperty=nameWithType>|<xref:Microsoft.Build.Conversion.ProjectFileConverter.ConvertInMemory%28Microsoft.Build.BuildEngine.Engine%29>|請改用無參數的 <xref:Microsoft.Build.Conversion.ProjectFileConverter.ConvertInMemory?displayProperty=nameWithType> 方法。|
|<xref:Microsoft.Build.Conversion.ProjectFileConverter?displayProperty=nameWithType>|<xref:Microsoft.Build.Conversion.ProjectFileConverter.ConvertInMemory%28Microsoft.Build.BuildEngine.Engine%2CMicrosoft.Build.BuildEngine.ProjectLoadSettings%29>|請改用無參數的 <xref:Microsoft.Build.Conversion.ProjectFileConverter.ConvertInMemory?displayProperty=nameWithType> 方法。|

<a name="engine"></a>

### <a name="assembly-microsoftbuildenginedll"></a>組件：Microsoft.Build.Engine.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:Microsoft.Build.BuildEngine.Engine?displayProperty=nameWithType>|<xref:Microsoft.Build.BuildEngine.Engine.BinPath%2A>|請避免設定 <xref:Microsoft.Build.BuildEngine.Engine.BinPath%2A>。 如果您只要傳入 .NET Framework 位置當做 <xref:Microsoft.Build.BuildEngine.Engine.BinPath%2A>，就不需要採取任何其他動作。 否則，請改為在登錄或組態檔中定義工具組，或將項目加入引擎的 <xref:Microsoft.Build.BuildEngine.ToolsetCollection?displayProperty=nameWithType>，以使用自訂 <xref:Microsoft.Build.BuildEngine.Engine.BinPath%2A>。|
|<xref:Microsoft.Build.BuildEngine.Engine?displayProperty=nameWithType>|<xref:Microsoft.Build.BuildEngine.Engine.%23ctor%28System.String%29>|如果您只要傳入 .NET Framework 位置當做 <xref:Microsoft.Build.BuildEngine.Engine.BinPath%2A>，只要變更為無參數的 <xref:Microsoft.Build.BuildEngine.Engine.%23ctor?displayProperty=nameWithType> 建構函式即可。 否則，您可以在登錄或組態檔中定義自訂工具組，或將項目加入引擎的 <xref:Microsoft.Build.BuildEngine.ToolsetCollection?displayProperty=nameWithType>。 然後，請改用 <xref:Microsoft.Build.BuildEngine.Engine.%23ctor?displayProperty=nameWithType> 或 <xref:Microsoft.Build.BuildEngine.Engine.%23ctor%28Microsoft.Build.BuildEngine.ToolsetDefinitionLocations%29?displayProperty=nameWithType> 建構函式。|

<a name="BuildFW"></a>

### <a name="assembly-microsoftbuildframeworkdll"></a>組件：Microsoft.Build.Framework.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:Microsoft.Build.Framework.XamlTypes.ContentType?displayProperty=nameWithType>|<xref:Microsoft.Build.Framework.XamlTypes.ContentType.ItemGroupName%2A>|在 .NET Framework 4.5 中首先被取代。<br /><br /> 使用這個成員會產生編譯器錯誤。<br /><br /> 請改用 <xref:Microsoft.Build.Framework.XamlTypes.ContentType.ItemType%2A?displayProperty=nameWithType> 屬性。|

<a name="BuildUtil4"></a>

### <a name="assembly-microsoftbuildutilitiesv40dll"></a>組件：Microsoft.Build.Utilities.v4.0.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:Microsoft.Build.Utilities.ToolTask?displayProperty=nameWithType>|<xref:Microsoft.Build.Utilities.ToolTask.EnvironmentOverride%2A>|請使用 <xref:Microsoft.Build.Utilities.ToolTask.EnvironmentVariables%2A?displayProperty=nameWithType> 屬性。|

<a name="data_entity_tasks"></a>

### <a name="assembly-microsoftdataentitybuildtasksdll"></a>組件：Microsoft.Data.Entity.Build.Tasks.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|`Microsoft.Data.Entity.Build.Tasks.EntityDeploy`|`EntityDataModelEmbeddedResources`|在 .NET Framework 4.5 中首先被取代。<br /><br /> 僅用於 3.5 版回溯相容性。|

<a name="visualbasic"></a>

### <a name="assembly-microsoftvisualbasicdll"></a>組件：Microsoft.VisualBasic.dll

|輸入|成員|訊息|
|----------|------------|-------------|
|<xref:Microsoft.VisualBasic.FileSystem?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.FileSystem.FilePut%28System.Object%2CSystem.Object%2CSystem.Object%29>|這個成員已被取代。 請使用 <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A?displayProperty=nameWithType> 來寫入 <xref:System.Object> 類型，或將 `FileNumber` 和 `RecordNumber` 強制轉型成 <xref:System.Int32>，以便寫入非物件類型。|
|<xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.CompilerServices.Conversions.FallbackUserDefinedConversion%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding.FallbackCall%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding.FallbackGet%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding.FallbackIndexSet%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding.FallbackIndexSetComplex%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding.FallbackInvokeDefault1%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding.FallbackInvokeDefault2%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding.FallbackSet%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding.FallbackSetComplex%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.CompilerServices.Operators.FallbackInvokeUserDefinedOperator%2A>|使用這個成員會產生編譯器錯誤。<br /><br /> 請勿使用這個方法。|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy?displayProperty=nameWithType>|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy.DynData%2A>|`DynData` 登錄機碼僅適用於 Win9x，不再受到這個 .NET Framework 版本的支援。 請改用 `PerformanceData` 登錄機碼。 這個屬性將從未來的 Framework 版本中移除。|

## <a name="see-also"></a>請參閱

- [類別庫中已淘汰的功能](whats-obsolete.md)
- [過時的類型](obsolete-types.md)
