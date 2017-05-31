---
title: Tipos obsoletos en .NET Framework | Microsoft Docs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework 4.5, obsolete types
- types, obsolete in .NET Framework 4.5
- obsolete types [.NET Framework]
ms.assetid: e636d024-0fac-45eb-b721-25a8c0ceca8f
caps.latest.revision: 41
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 01c66e2c291766ba00376261740906934f065855
ms.openlocfilehash: b7040d4c82c9434b2d24a579a93602660479ec59
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="obsolete-types-in-the-net-framework"></a>Tipos obsoletos en .NET Framework
<a name="introduction"></a> En las tablas de este artículo se muestran los tipos que están obsoletos en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] y [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] organizados por ensamblados. Utilice los vínculos siguientes para ver una lista de tipos obsoletos y las alternativas recomendadas en cada ensamblado. Dado que estos tipos están en desuso, todos sus miembros también lo están. Para obtener una lista de miembros obsoletos adicionales de la biblioteca de clases de .NET Framework, vea [Miembros obsoletos](../../../docs/framework/whats-new/obsolete-members.md).  
  
-   [Tipos obsoletos en ensamblados del sistema](#obsolete_types_in_system_assemblies)  
  
    -   [mscorlib.dll](#mscorlib)  
  
    -   [System.Core.dll](#Core)  
  
    -   [System.Data.dll](#data)  
  
    -   [System.Data.OracleClient.dll](#oracleclient)  
  
    -   [System.Design.dll](#design)  
  
    -   [System.dll](#system)  
  
    -   [System.EnterpriseServices.dll](#enterpriseservices)  
  
    -   [System.Net.dll](#net)  
  
    -   [System.ServiceModel.dll](#servicemodel)  
  
    -   [System.Web.dll](#web)  
  
    -   [System.Web.Mobile.dll](#mobile)  
  
    -   [System.Workflow.Activities.dll](#workflow_activities)  
  
    -   [System.Workflow.ComponentModel.dll](#workflow_componentmodel)  
  
    -   [System.Workflow.Runtime.dll](#workflow_runtime)  
  
    -   [System.WorkflowServices.dll](#workflowservices)  
  
    -   [System.Xaml.dll](#xaml)  
  
    -   [System.Xml.dll](#xml)  
  
    -   [WindowsBase.dll](#WindowsBase)  
  
-   [Tipos obsoletos en ensamblados de Microsoft](#obsolete_types_in_microsoft_assemblies)  
  
    -   [IEHost.dll e IEExec.exe](#IEHost)  
  
    -   [Microsoft.Build.Engine.dll](#Engine)  
  
    -   [Microsoft.JScript.dll](#jscript)  
  
    -   [Microsoft.VisualBasic.Compatibility.dll](#VBCompat)  
  
    -   [Microsoft.VisualBasic.Compatibility.Data.dll](#VBCompatData)  
  
    -   [Microsoft.VisualC.dll](#visualc)  
  
<a name="obsolete_types_in_system_assemblies"></a>   
## <a name="obsolete-types-in-system-assemblies"></a>Tipos obsoletos en ensamblados del sistema  
 En las tablas siguientes se enumeran los tipos que se han declarado obsoletos en ensamblados del sistema. Estos ensamblados se usan para el desarrollo de aplicaciones de uso\-general cuyo destino es .NET Framework.  
  
<a name="mscorlib"></a>   
### <a name="assembly-mscorlibdll"></a>Ensamblado: mscorlib.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.ExecutionEngineException?displayProperty=fullName>|Este tipo indicaba anteriormente un error irrecuperable no especificado en el runtime. El runtime ya no produce esta excepción, por lo que este tipo queda obsoleto.|  
|<xref:System.Collections.CaseInsensitiveHashCodeProvider?displayProperty=fullName>|Use <xref:System.StringComparer?displayProperty=fullName> en su lugar.|  
|<xref:System.Collections.IHashCodeProvider?displayProperty=fullName>|Use <xref:System.Collections.IEqualityComparer?displayProperty=fullName> en su lugar.|  
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=fullName>|La clase <xref:System.Configuration.Assemblies.AssemblyHash> está desusada.|  
|<xref:System.Diagnostics.Contracts.Internal.ContractHelper?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5. Use la clase <xref:System.Runtime.CompilerServices.ContractHelper?displayProperty=fullName> del espacio de nombres System.Runtime.CompilerServices en su lugar.|  
|<xref:System.Reflection.Emit.UnmanagedMarshal?displayProperty=fullName>|Hay una API alternativa disponible: emita el atributo personalizado <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.BIND_OPTS?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.BIND_OPTS?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.BINDPTR?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.BINDPTR?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.CALLCONV?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.CALLCONV?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.CONNECTDATA?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.CONNECTDATA?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.DESCKIND?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.DESCKIND?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.DISPPARAMS?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.DISPPARAMS?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.ELEMDESC?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.ELEMDESC?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.EXCEPINFO?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.EXCEPINFO?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.FILETIME?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.FILETIME?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.FUNCDESC?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.FUNCDESC?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.FUNCFLAGS?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.FUNCFLAGS?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.FUNCKIND?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.FUNCKIND?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=fullName>|Este atributo está en desuso y se quitará en futuras versiones.|  
|<xref:System.Runtime.InteropServices.IDispatchImplType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=fullName> está desusado.|  
|<xref:System.Runtime.InteropServices.IDLDESC?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IDLDESC?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.IDLFLAG?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IDLFLAG?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.IMPLTYPEFLAGS?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IMPLTYPEFLAGS?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.INVOKEKIND?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.INVOKEKIND?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.LIBFLAGS?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.LIBFLAGS?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.PARAMDESC?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.PARAMDESC?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.PARAMFLAG?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.PARAMFLAG?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.SetWin32ContextInIDispatchAttribute?displayProperty=fullName>|Este atributo está en desuso. Los dominios de aplicación ya no tienen en cuenta los límites del contexto de activación en las llamadas de IDispatch.|  
|<xref:System.Runtime.InteropServices.STATSTG?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.STATSTG?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.SYSKIND?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.SYSKIND?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.TYPEATTR?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.TYPEATTR?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.TYPEDESC?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.TYPEDESC?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.TYPEFLAGS?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.TYPEFLAGS?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.TYPEKIND?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.TYPEKIND?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.TYPELIBATTR?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.TYPELIBATTR?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMIBindCtx?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IBindCtx?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMIConnectionPoint?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMIConnectionPointContainer?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumConnectionPoints?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IEnumConnectionPoints?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumConnections?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IEnumConnections?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumMoniker?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IEnumMoniker?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumString?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IEnumString?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumVARIANT?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMIMoniker?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IMoniker?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMIPersistFile?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IPersistFile?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMIRunningObjectTable?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IRunningObjectTable?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMIStream?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMITypeComp?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.ITypeComp?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMITypeInfo?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.UCOMITypeLib?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.ITypeLib?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.VARDESC?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.VARDESC?displayProperty=fullName> en su lugar.|  
|<xref:System.Runtime.InteropServices.VARFLAGS?displayProperty=fullName>|Utilice <xref:System.Runtime.InteropServices.ComTypes.VARFLAGS?displayProperty=fullName> en su lugar.|  
|<xref:System.Security.SecurityCriticalScope?displayProperty=fullName>|<xref:System.Security.SecurityCriticalScope> solo se utiliza para la compatibilidad de transparencia con .NET 2.0.|  
|<xref:System.Security.SecurityTreatAsSafeAttribute?displayProperty=fullName>|<xref:System.Security.SecurityTreatAsSafeAttribute> solo se utiliza para la compatibilidad de transparencia con .NET 2.0. Utilice <xref:System.Security.SecuritySafeCriticalAttribute?displayProperty=fullName> en su lugar.|  
|<xref:System.Security.Policy.FirstMatchCodeGroup?displayProperty=fullName>|Este tipo está obsoleto y se quitará en futuras versiones de .NET Framework.|  
|<xref:System.Security.Policy.PermissionRequestEvidence?displayProperty=fullName>|La seguridad declarativa de nivel de ensamblado está obsoleta y CLR ya no la exige de manera predeterminada.|  
|<xref:System.Security.Policy.UnionCodeGroup?displayProperty=fullName>|Este tipo está obsoleto y se quitará en futuras versiones de .NET Framework.|  
  
 [Volver al principio](#introduction)  
  
<a name="Core"></a>   
### <a name="assembly-systemcoredll"></a>Ensamblado: System.Core.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.Runtime.CompilerServices.ExecutionScope?displayProperty=fullName>|El uso de este tipo genera un error del compilador.<br /><br /> No use este tipo.|  
  
 [Volver al principio](#introduction)  
  
<a name="data"></a>   
### <a name="assembly-systemdatadll"></a>Ensamblado: System.Data.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.Data.DataSysDescriptionAttribute?displayProperty=fullName>|<xref:System.Data.DataSysDescriptionAttribute> está desusado.|  
|<xref:System.Data.PropertyAttributes?displayProperty=fullName>|<xref:System.Data.PropertyAttributes> está desusado.|  
|<xref:System.Data.TypedDataSetGenerator?displayProperty=fullName>|La clase <xref:System.Data.TypedDataSetGenerator> se quitará en futuras versiones. Utilice <xref:System.Data.Design.TypedDataSetGenerator?displayProperty=fullName> en System.Design.dll.|  
|<xref:System.Xml.XmlDataDocument?displayProperty=fullName>|La clase <xref:System.Xml.XmlDataDocument> se quitará en futuras versiones.|  
  
 [Volver al principio](#introduction)  
  
<a name="oracleclient"></a>   
### <a name="assembly-systemdataoracleclientdll"></a>Ensamblado: System.Data.OracleClient.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.Data.OracleClient.OracleClientFactory?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleClientFactory> está desusado.|  
|<xref:System.Data.OracleClient.OracleCommand?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleCommand> está desusado.|  
|<xref:System.Data.OracleClient.OracleCommandBuilder?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleCommandBuilder> está desusado.|  
|<xref:System.Data.OracleClient.OracleConnection?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleConnection> está desusado.|  
|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder> está desusado.|  
|<xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleDataAdapter> está desusado.|  
|<xref:System.Data.OracleClient.OraclePermission?displayProperty=fullName>|<xref:System.Data.OracleClient.OraclePermission> está desusado.|  
|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=fullName>|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=fullName> está desusado.|  
  
 [Volver al principio](#introduction)  
  
<a name="design"></a>   
### <a name="assembly-systemdesigndll"></a>Ensamblado: System.Design.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.ComponentModel.Design.LocalizationExtenderProvider?displayProperty=fullName>|Esta clase está desusada. Utilice <xref:System.ComponentModel.Design.Serialization.CodeDomLocalizationProvider?displayProperty=fullName> en su lugar.|  
|<xref:System.Web.UI.Design.DataBindingCollectionConverter?displayProperty=fullName>|No se recomienda el uso de este tipo porque la edición de DataBindings se inicia mediante <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=fullName> en lugar de la cuadrícula de propiedades.|  
|<xref:System.Web.UI.Design.DataBindingCollectionEditor?displayProperty=fullName>|No se recomienda el uso de este tipo porque la edición de DataBindings se inicia mediante <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=fullName> en lugar de la cuadrícula de propiedades.|  
|<xref:System.Web.UI.Design.IControlDesignerBehavior?displayProperty=fullName>|La alternativa recomendada es <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=fullName> y <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.IHtmlControlDesignerBehavior?displayProperty=fullName>|La alternativa recomendada es <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=fullName> y <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.ITemplateEditingFrame?displayProperty=fullName>|No se recomienda el uso de este tipo porque la edición de plantillas se controla en <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>. Para admitir la edición de plantillas, exponga los datos de la plantilla en la propiedad <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName> y llame al método <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.IWebFormReferenceManager?displayProperty=fullName>|La alternativa recomendada es <xref:System.Web.UI.Design.WebFormsReferenceManager?displayProperty=fullName>. <xref:System.Web.UI.Design.WebFormsReferenceManager> contiene funcionalidad adicional y permite más extensibilidad. Para obtener <xref:System.Web.UI.Design.WebFormsReferenceManager>, utilice la propiedad `RootDesigner.ReferenceManager` de <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.IWebFormsDocumentService?displayProperty=fullName>|La alternativa recomendada es <xref:System.Web.UI.Design.WebFormsRootDesigner?displayProperty=fullName>. <xref:System.Web.UI.Design.WebFormsRootDesigner> contiene funcionalidad adicional y permite más extensibilidad. Para obtener <xref:System.Web.UI.Design.WebFormsRootDesigner>, utilice la propiedad <xref:System.Web.UI.Design.ControlDesigner.RootDesigner%2A> de <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.ITemplateEditingService?displayProperty=fullName>|No se recomienda el uso de este tipo porque la edición de plantillas se controla en <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>. Para admitir la edición de plantillas, exponga los datos de la plantilla en la propiedad <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName> y llame al método <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.ReadWriteControlDesigner?displayProperty=fullName>|La alternativa recomendada es <xref:System.Web.UI.Design.ContainerControlDesigner?displayProperty=fullName> porque utiliza un objeto <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=fullName> para editar el contenido. Las regiones del diseñador permiten un control mejor del contenido que se va a editar.|  
|<xref:System.Web.UI.Design.TemplateEditingService?displayProperty=fullName>|No se recomienda el uso de este tipo porque la edición de plantillas se controla en <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>. Para admitir la edición de plantillas, exponga los datos de la plantilla en la propiedad <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName> y llame al método <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.TemplateEditingVerb?displayProperty=fullName>|No se recomienda el uso de este tipo porque la edición de plantillas se controla en <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>. Para admitir la edición de plantillas, exponga los datos de la plantilla en la propiedad <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName> y llame al método <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.WebControls.CalendarAutoFormatDialog?displayProperty=fullName>|No se recomienda el uso de este tipo porque el host del diseñador inicia el cuadro de diálogo Autoformato. La lista de autoformatos disponibles se expone en el objeto <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName> en la propiedad <xref:System.Web.UI.Design.ControlDesigner.AutoFormats%2A?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.WebControls.PanelDesigner?displayProperty=fullName>|La alternativa recomendada es <xref:System.Web.UI.Design.WebControls.PanelContainerDesigner?displayProperty=fullName> porque utiliza un objeto <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=fullName> para editar el contenido. Las regiones del diseñador permiten un control mejor del contenido que se va a editar.|  
  
 [Volver al principio](#introduction)  
  
<a name="system"></a>   
### <a name="assembly-systemdll"></a>Ensamblado: System.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.ComponentModel.IComNativeDescriptorHandler?displayProperty=fullName>|Esta interfaz está desusada. En su lugar, agregue un objeto <xref:System.ComponentModel.TypeDescriptionProvider?displayProperty=fullName> para controlar el tipo <xref:System.ComponentModel.TypeDescriptor.ComObjectType%2A?displayProperty=fullName>.|  
|<xref:System.ComponentModel.RecommendedAsConfigurableAttribute?displayProperty=fullName>|Utilice <xref:System.ComponentModel.SettingsBindableAttribute?displayProperty=fullName> en su lugar para trabajar con el nuevo modelo de configuración.|  
|<xref:System.ComponentModel.Design.Serialization.RootDesignerSerializerAttribute?displayProperty=fullName>|Este atributo está obsoleto. Utilice <xref:System.ComponentModel.Design.Serialization.DesignerSerializerAttribute?displayProperty=fullName> en su lugar. Por ejemplo, para especificar un diseñador raíz de CodeDom, utilice `DesignerSerializerAttribute\(...,typeof\(TypeCodeDomSerializer\)\)`.|  
|<xref:System.Diagnostics.DiagnosticsConfigurationHandler?displayProperty=fullName>|Esta clase está en desuso.|  
|<xref:System.Diagnostics.PerformanceCounterManager?displayProperty=fullName>|Esta clase está desusada. Utilice los contadores de rendimiento a través de la clase <xref:System.Diagnostics.PerformanceCounter?displayProperty=fullName> en su lugar.|  
|<xref:System.Net.GlobalProxySelection?displayProperty=fullName>|Esta clase está en desuso. Utilice <xref:System.Net.WebRequest.DefaultWebProxy%2A?displayProperty=fullName> en su lugar para obtener acceso al proxy global predeterminado y establecerlo. Use "null" en lugar de <xref:System.Net.GlobalProxySelection.GetEmptyWebProxy%2A?displayProperty=fullName>.|  
|<xref:System.Net.Sockets.SocketClientAccessPolicyProtocol?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|  
  
 [Volver al principio](#introduction)  
  
<a name="enterpriseservices"></a>   
### <a name="assembly-systementerpriseservicesdll"></a>Ensamblado: System.EnterpriseServices.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.EnterpriseServices.RegistrationHelperTx?displayProperty=fullName>|La clase <xref:System.EnterpriseServices.RegistrationHelperTx> está desusada.|  
  
 [Volver al principio](#introduction)  
  
<a name="net"></a>   
### <a name="assembly-systemnetdll"></a>Ensamblado: System.Net.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.Net.INetworkProgress?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|  
|<xref:System.Net.IUnsafeWebRequestCreate?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|  
|<xref:System.Net.NetworkProgressChangedEventArgs?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|  
|<xref:System.Net.UiSynchronizationContext?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|  
|<xref:System.Net.Sockets.HttpPolicyDownloaderProtocol?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|  
|<xref:System.Net.Sockets.SecurityCriticalAction?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|  
|<xref:System.Net.Sockets.SocketPolicy?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|  
|<xref:System.Net.Sockets.UdpAnySourceMulticastClient?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|  
|<xref:System.Net.Sockets.UdpSingleSourceMulticastClient?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|  
  
 [Volver al principio](#introduction)  
  
<a name="servicemodel"></a>   
### <a name="assembly-systemservicemodeldll"></a>Ensamblado: System.ServiceModel.Channels.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.ServiceModel.NetPeerTcpBinding?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|  
|<xref:System.ServiceModel.Channels.HttpCookieContainerBindingElement?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Este tipo está obsoleto. Para habilitar el objeto <xref:System.Net.CookieContainer> de HTTP, utilice la propiedad `AllowCookies` del enlace HTTP o del objeto <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.|  
|<xref:System.ServiceModel.Channels.PeerCustomResolverBindingElement?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|  
|<xref:System.ServiceModel.Channels.PeerTransportBindingElement?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|  
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingCollectionElement?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|  
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|  
|<xref:System.ServiceModel.Configuration.PeerTransportElement?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|  
|<xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|  
  
 [Volver al principio](#introduction)  
  
<a name="web"></a>   
### <a name="assembly-systemwebdll"></a>Ensamblado: System.Web.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.Web.Configuration.PassportAuthentication?displayProperty=fullName>|Este tipo está obsoleto. El producto de autenticación mediante Passport ya no se admite y se ha sustituido por la [cuenta Microsoft](http://go.microsoft.com/fwlink/?LinkId=733413).|  
|<xref:System.Web.Mail.MailAttachment?displayProperty=fullName>|La alternativa recomendada es <xref:System.Net.Mail.Attachment?displayProperty=fullName>.|  
|<xref:System.Web.Mail.MailEncoding?displayProperty=fullName>|La alternativa recomendada es <xref:System.Net.Mime.TransferEncoding?displayProperty=fullName>.|  
|<xref:System.Web.Mail.MailFormat?displayProperty=fullName>|La alternativa recomendada es <xref:System.Net.Mail.MailMessage.IsBodyHtml%2A?displayProperty=fullName>.|  
|<xref:System.Web.Mail.MailMessage?displayProperty=fullName>|La alternativa recomendada es <xref:System.Net.Mail.MailMessage?displayProperty=fullName>.|  
|<xref:System.Web.Mail.MailPriority?displayProperty=fullName>|La alternativa recomendada es <xref:System.Net.Mail.MailPriority?displayProperty=fullName>.|  
|<xref:System.Web.Mail.SmtpMail?displayProperty=fullName>|La alternativa recomendada es <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>.|  
|<xref:System.Web.Security.PassportAuthenticationEventArgs?displayProperty=fullName>|Este tipo está obsoleto. El producto de autenticación mediante Passport ya no se admite y se ha sustituido por la [cuenta Microsoft](http://go.microsoft.com/fwlink/?LinkId=733413).|  
|<xref:System.Web.Security.PassportAuthenticationEventHandler?displayProperty=fullName>|Este tipo está obsoleto. El producto de autenticación mediante Passport ya no se admite y se ha sustituido por la [cuenta Microsoft](http://go.microsoft.com/fwlink/?LinkId=733413).|  
|<xref:System.Web.Security.PassportAuthenticationModule?displayProperty=fullName>|Este tipo está obsoleto. El producto de autenticación mediante Passport ya no se admite y se ha sustituido por la [cuenta Microsoft](http://go.microsoft.com/fwlink/?LinkId=733413).|  
|<xref:System.Web.Security.PassportIdentity?displayProperty=fullName>|Este tipo está obsoleto. El producto de autenticación mediante Passport ya no se admite y se ha sustituido por la [cuenta Microsoft](http://go.microsoft.com/fwlink/?LinkId=733413).|  
|<xref:System.Web.Security.PassportPrincipal?displayProperty=fullName>|Este tipo está obsoleto. El producto de autenticación mediante Passport ya no se admite y se ha sustituido por la [cuenta Microsoft](http://go.microsoft.com/fwlink/?LinkId=733413).|  
|<xref:System.Web.UI.ObjectConverter?displayProperty=fullName>|La alternativa recomendada es <xref:System.Convert?displayProperty=fullName> y <xref:System.String.Format%2A?displayProperty=fullName>.|  
  
 [Volver al principio](#introduction)  
  
<a name="mobile"></a>   
### <a name="assembly-systemwebmobiledll"></a>Ensamblado: System.Web.Mobile.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.Web.Mobile.CookielessData?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.DeviceFilterElement?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.DeviceFilterElementCollection?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.DeviceFiltersSection?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.ErrorHandlerModule?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.MobileCapabilities?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.MobileDeviceCapabilitiesSectionHandler?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.MobileErrorInfo?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.MobileFormsAuthentication?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.IMobileDesigner?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.IMobileWebFormServices?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.MobileResource?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.Converters.DataFieldConverter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.Converters.DataMemberConverter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.AdRotator?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Alignment?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ArrayListCollectionBase?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.BaseValidator?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.BooleanOption?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Calendar?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Command?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.CommandFormat?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.CompareValidator?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Constants?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ControlElement?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ControlElementCollection?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ControlPager?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.CustomValidator?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DesignerAdapterAttribute?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceElement?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceElementCollection?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceOverridableAttribute?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecific?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoice?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceCollection?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceControlBuilder?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateBuilder?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateContainer?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificControlBuilder?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ErrorFormatterPage?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.FontInfo?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.FontSize?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Form?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.FormControlBuilder?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.FormMethod?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.IControlAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Image?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.IObjectListFieldCollection?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.IPageAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ItemPager?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ITemplateable?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Label?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Link?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.List?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListCommandEventArgs?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListCommandEventHandler?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListControlBuilder?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListDataBindEventArgs?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListDataBindEventHandler?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListDecoration?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListSelectType?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LiteralLink?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LiteralText?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LiteralTextContainerControlBuilder?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LiteralTextControlBuilder?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LoadItemsEventArgs?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LoadItemsEventHandler?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileControl?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileControlBuilder?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileControlsSection?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileControlsSectionHandler?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileListItem?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileListItemCollection?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileListItemType?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobilePage?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileTypeNameConverter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileUserControl?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectList?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListCommand?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListCommandCollection?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventArgs?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventHandler?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListControlBuilder?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventArgs?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventHandler?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListField?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListFieldCollection?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListItem?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListItemCollection?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventArgs?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventHandler?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventArgs?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventHandler?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListTitleAttribute?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListViewMode?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PagedControl?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PagerStyle?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Panel?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PanelControlBuilder?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PersistNameAttribute?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PhoneCall?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.RangeValidator?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.RegularExpressionValidator?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.RequiredFieldValidator?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.SelectionList?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Style?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.StyleSheet?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.StyleSheetControlBuilder?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TemplateContainer?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextBox?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextBoxControlBuilder?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextControl?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextView?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextViewElement?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ValidationSummary?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Wrapping?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCalendarAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCommandAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlFormAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlImageAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlLinkAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlMobileTextWriter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPageAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPhoneCallAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlSelectionListAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlTextBoxAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ControlAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCalendarAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCommandAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlControlAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlFormAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlImageAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLabelAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLinkAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlListAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLiteralTextAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlMobileTextWriter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlObjectListAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPageAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPanelAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPhoneCallAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlSelectionListAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextBoxAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextViewAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidationSummaryAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidatorAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.MobileTextWriter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.MultiPartWriter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlMobileTextWriter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlPageAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlCalendarAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlCommandAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlControlAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlFormAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlImageAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlLabelAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlLinkAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlListAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlLiteralTextAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlMobileTextWriter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlObjectListAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPageAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPanelAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPhoneCallAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPostFieldType?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlSelectionListAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextBoxAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextViewAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidationSummaryAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidatorAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.Doctype?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.StyleSheetLocation?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCalendarAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCommandAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlControlAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCssHandler?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlFormAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlImageAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLabelAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLinkAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlListAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLiteralTextAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlMobileTextWriter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlObjectListAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPageAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPanelAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPhoneCallAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlSelectionListAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextBoxAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextViewAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidationSummaryAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidatorAdapter?displayProperty=fullName>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](http://go.microsoft.com/fwlink/?LinkId=157231).|  
  
 [Volver al principio](#introduction)  
  
<a name="workflow_activities"></a>   
### <a name="assembly-systemworkflowactivitiesdll"></a>Ensamblado: System.Workflow.Activities.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|Todos los tipos del espacio de nombres <xref:System.Workflow.Activities?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Activities.Configuration.ActiveDirectoryRoleFactoryConfiguration?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Activities.Rules.RuleActionTrackingEvent?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Activities.Rules.RuleConditionReference?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Activities.Rules.RuleSetReference?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
  
 [Volver al principio](#introduction)  
  
<a name="workflow_componentmodel"></a>   
### <a name="assembly-systemworkflowcomponentmodeldll"></a>Ensamblado: System.Workflow.ComponentModel.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|Todos los tipos del espacio de nombres <xref:System.Workflow.ComponentModel> excepto <xref:System.Workflow.ComponentModel.GetValueOverride?displayProperty=fullName> y <xref:System.Workflow.ComponentModel.SetValueOverride?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|Todos los tipos del espacio de nombres <xref:System.Workflow.ComponentModel.Compiler> excepto <xref:System.Workflow.ComponentModel.Compiler.ValidationError?displayProperty=fullName> y <xref:System.Workflow.ComponentModel.Compiler.ValidationErrorCollection?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|Todos los tipos del espacio de nombres <xref:System.Workflow.ComponentModel.Design> excepto <xref:System.Workflow.ComponentModel.Design.ConnectorEventHandler>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializationManager?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializer?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityMarkupSerializer?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivitySurrogateSelector?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityTypeCodeDomSerializer?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.CompositeActivityMarkupSerializer?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.DependencyObjectCodeDomSerializer?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
  
 [Volver al principio](#introduction)  
  
<a name="workflow_runtime"></a>   
### <a name="assembly-systemworkflowruntimedll"></a>Ensamblado: System.Workflow.Runtime.dll  
  
|Tipo|Mensaje|  
|----------|-------------| 
|<xref:System.Activities.Statements.Interop>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br />Los tipos de Workflow Foundation 3.0 están desusados. En su lugar, use los tipos de Workflow 4.0 de <xref:System.Activities>.\*.|  
|<xref:System.Activities.Tracking.InteropTrackingRecord>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br />Los tipos de Workflow Foundation 3.0 están desusados. En su lugar, use los tipos de Workflow 4.0 de <xref:System.Activities>.\*.|   
|Todos los tipos del espacio de nombres <xref:System.Workflow.Runtime>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|Todos los tipos del espacio de nombres <xref:System.Workflow.Runtime.Configuration>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|Todos los tipos del espacio de nombres <xref:System.Workflow.Runtime.DebugEngine> excepto <xref:System.Workflow.Runtime.DebugEngine.DebugEngineCallback>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|Todos los tipos del espacio de nombres <xref:System.Workflow.Runtime.Hosting> excepto <xref:System.Workflow.Runtime.Hosting.WorkflowCommitWorkBatchService.CommitWorkBatchCallback>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
|Todos los tipos del espacio de nombres <xref:System.Workflow.Runtime.Tracking>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos System.Workflow.\* están desusados. En su lugar, use los nuevos tipos de <xref:System.Activities>.\*.|  
  
 [Volver al principio](#introduction)  
  
<a name="workflowservices"></a>   
### <a name="assembly-systemworkflowservicesdll"></a>Ensamblado: System.WorkflowServices.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.ServiceModel.WorkflowServiceHost?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Activation.WorkflowServiceHostFactory?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Activities.Description.WorkflowRuntimeEndpoint?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Configuration.ExtendedWorkflowRuntimeServiceElementCollection?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Configuration.PersistenceProviderElement?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Configuration.WorkflowRuntimeElement?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.DurableOperationAttribute?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.DurableServiceAttribute?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.PersistenceProviderBehavior?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.UnknownExceptionAction?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.WorkflowRuntimeBehavior?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Dispatcher.DurableOperationContext?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.InstanceLockException?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.InstanceNotFoundException?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.LockingPersistenceProvider?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.PersistenceException?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.PersistenceProvider?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.PersistenceProviderFactory?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.SqlPersistenceProviderFactory?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|Todos los tipos del espacio de nombres <xref:System.Workflow.Activities?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Runtime.Hosting.ChannelManagerService?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>.\*.|  
  
 [Volver al principio](#introduction)  
  
<a name="xaml"></a>   
### <a name="assembly-systemxamldll"></a>Ensamblado: System.Xaml.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute?displayProperty=fullName>|Este tipo no lo utiliza el analizador de XAML. Consulte <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute?displayProperty=fullName>.|  
  
 [Volver al principio](#introduction)  
  
<a name="xml"></a>   
### <a name="assembly-systemxmldll"></a>Ensamblado: System.Xml.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.Xml.IApplicationResourceStreamResolver?displayProperty=fullName>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|  
|<xref:System.Xml.Schema.XmlSchemaCollection?displayProperty=fullName>|Use <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=fullName> para la compilación y validación de esquema.|  
|<xref:System.Xml.XmlValidatingReader?displayProperty=fullName>|Utilice un objeto <xref:System.Xml.XmlReader?displayProperty=fullName> creado por el método <xref:System.Xml.XmlReader.Create%2A?displayProperty=fullName> que utilice en su lugar el objeto <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> apropiado.|  
|<xref:System.Xml.XmlXapResolver?displayProperty=fullName>|El uso de este tipo genera un error del compilador. Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|  
|<xref:System.Xml.Xsl.XslTransform?displayProperty=fullName>|Esta clase está desusada. Use <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=fullName> en su lugar.|  
  
 [Volver al principio](#introduction)  
  
<a name="WindowsBase"></a>   
### <a name="assembly-windowsbasedll"></a>Ensamblado: WindowsBase.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=fullName>|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=fullName> está desusado. Esta interfaz ya no se utiliza.|  
  
 [Volver al principio](#introduction)  
  
<a name="obsolete_types_in_microsoft_assemblies"></a>   
## <a name="obsolete-types-in-microsoft-assemblies"></a>Tipos obsoletos en ensamblados de Microsoft  
 En las secciones siguientes se enumeran los tipos obsoletos en ensamblados de Microsoft. Estos ensamblados son ensamblados para fines especiales, como ensamblados que están destinados a un lenguaje individual (por ejemplo, Microsoft.JScript.dll o Microsoft.VisualC.dll).  
  
<a name="IEHost"></a>   
### <a name="assembly-iehostdll-and-ieexecexe"></a>Ensamblado: IEHost.dll e IEExec.exe  
 Se han quitado de .NET Framework los ensamblados IEHost.dll e IEExec.exe. Todos sus tipos y sus miembros están obsoletos y no se admiten a partir de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]. Estos ensamblados se utilizaban para hospedar los controles de Windows Forms y ejecutar las aplicaciones ejecutables en Internet Explorer. Entre las alternativas recomendadas se incluye ClickOnce, aplicaciones de explorador XAML (XBAP) y Microsoft Silverlight.  
  
 [Volver al principio](#introduction)  
  
<a name="Engine"></a>   
### <a name="assembly-microsoftbuildenginedll"></a>Ensamblado: Microsoft.Build.Engine.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:Microsoft.Build.BuildEngine.Engine?displayProperty=fullName>|Esta clase está en desuso. Use <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=fullName> del ensamblado *Microsoft.Build* en su lugar.|  
|<xref:Microsoft.Build.BuildEngine.Project?displayProperty=fullName>|Esta clase está en desuso. Use <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=fullName> del ensamblado *Microsoft.Build* en su lugar.|  
  
 [Volver al principio](#introduction)  
  
<a name="jscript"></a>   
### <a name="assembly-microsoftjscriptdll"></a>Ensamblado: Microsoft.JScript.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:Microsoft.JScript.Vsa.BaseVsaEngine?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.BaseVsaSite?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.BaseVsaStartup?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaCodeItem?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaEngine?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaError?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaGlobalItem?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaItem?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaItems?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaPersistSite?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaReferenceItem?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaSite?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.JSVsaError?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.JSVsaException?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.JSVsaItemFlag?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.JSVsaItemType?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.ResInfo?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
|<xref:Microsoft.JScript.Vsa.VsaEngine?displayProperty=fullName>|No se recomienda el uso de este tipo porque está en desuso en Visual Studio 2005; no hay ningún reemplazo para esta característica. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> para obtener información adicional.|  
  
 [Volver al principio](#introduction)  
  
<a name="VBCompat"></a>   
### <a name="assembly-microsoftvisualbasiccompatibilitydll"></a>Ensamblado: Microsoft.VisualBasic.Compatibility.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseControlArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseOcxArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ButtonArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckBoxArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckedListBoxArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ColorDialogArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ComboBoxArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBox?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBoxArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBox?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBoxArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBox?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBoxArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FixedLengthString?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FontDialogArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FormShowConstants?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.GroupBoxArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.HScrollBarArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ImageListArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LabelArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxItem?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListViewArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LoadResConstants?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MaskedTextBoxArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MenuItemArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MouseButtonConstants?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.OpenFileDialogArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PanelArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PictureBoxArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PrintDialogArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ProgressBarArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RadioButtonArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RichTextBoxArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SaveFileDialogArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ScaleMode?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ShiftConstants?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusBarArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusStripArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.Support?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TabControlArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TextBoxArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TimerArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolBarArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripMenuItemArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TreeViewArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.VScrollBarArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebBrowserArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClass?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassContainingClassNotOptional?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassCouldNotFindEvent?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemCannotBeCurrentWebItem?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemRespondNotFound?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassUserWebClassNameNotOptional?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebClassFileNameNotOptional?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebItemNotValid?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItem?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemAssociatedWebClassNotOptional?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemClosingTagNotFound?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadEmbeddedResource?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadTemplateFile?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNameNotOptional?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNoTemplateSpecified?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemTooManyNestedTags?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemUnexpectedErrorReadingTemplateFile?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ZOrderConstants?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
  
 [Volver al principio](#introduction)  
  
<a name="VBCompatData"></a>   
### <a name="assembly-microsoftvisualbasiccompatibilitydatadll"></a>Ensamblado: Microsoft.VisualBasic.Compatibility.Data.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.BOFActionEnum?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EndOfRecordsetDelegate?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EOFActionEnum?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.ErrorDelegate?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchCompleteDelegate?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchProgressDelegate?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FieldChangeCompleteDelegate?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.MoveCompleteDelegate?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.OrientationEnum?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordChangeCompleteDelegate?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordsetChangeCompleteDelegate?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeFieldDelegate?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordDelegate?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordsetDelegate?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillMoveDelegate?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODCArray?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseDataEnvironment?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BindingCollectionEnumerator?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CONNECTDATA?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBBINDING?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBCOLUMNINFO?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBID?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBinding?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBindingCollection?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBKINDENUM?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBPROPIDSET?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IAccessor?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IChapteredRowset?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IColumnsInfo?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPoint?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPointContainer?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormat?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormatDisp?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnectionPoints?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnections?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPosition?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPositionChange?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowset?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetChange?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetIdentity?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetInfo?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetNotify?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBinding?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBindingCollection?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SRDescriptionAttribute?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UGUID?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UNAME?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UpdateMode?displayProperty=fullName>|Vea [Microsoft.VisualBasic.Compatibility.VB6.\<miembro> está obsoleto y solo se admite en procesos de 32 bits](https://msdn.microsoft.com/library/ee839621.aspx).|  
  
 [Volver al principio](#introduction)  
  
<a name="visualc"></a>   
### <a name="assembly-microsoftvisualcdll"></a>Ensamblado: Microsoft.VisualC.dll  
  
|Tipo|Mensaje|  
|----------|-------------|  
|<xref:Microsoft.VisualC.DebugInfoInPDBAttribute?displayProperty=fullName>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|  
|<xref:Microsoft.VisualC.DecoratedNameAttribute?displayProperty=fullName>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|  
|<xref:Microsoft.VisualC.IsConstModifier?displayProperty=fullName>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|  
|<xref:Microsoft.VisualC.IsCXXReferenceModifier?displayProperty=fullName>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|  
|<xref:Microsoft.VisualC.IsLongModifier?displayProperty=fullName>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|  
|<xref:Microsoft.VisualC.IsSignedModifier?displayProperty=fullName>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|  
|<xref:Microsoft.VisualC.IsVolatileModifier?displayProperty=fullName>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|  
|<xref:Microsoft.VisualC.MiscellaneousBitsAttribute?displayProperty=fullName>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|  
|<xref:Microsoft.VisualC.NeedsCopyConstructorModifier?displayProperty=fullName>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|  
|<xref:Microsoft.VisualC.NoSignSpecifiedModifier?displayProperty=fullName>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|  
  
## <a name="see-also"></a>Vea también  
 [Lo obsoleto en la biblioteca de clases](../../../docs/framework/whats-new/whats-obsolete.md)   
 [Miembros obsoletos](../../../docs/framework/whats-new/obsolete-members.md)

