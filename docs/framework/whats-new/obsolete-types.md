---
title: Tipos obsoletos en .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, obsolete types
- types, obsolete in .NET Framework 4.5
- obsolete types [.NET Framework]
ms.assetid: e636d024-0fac-45eb-b721-25a8c0ceca8f
ms.openlocfilehash: b7932a553f39e1f1da2a3946878d6224099da8da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74802692"
---
# <a name="obsolete-types-in-the-net-framework"></a>Tipos obsoletos en .NET Framework

<a name="introduction"></a> En las tablas de este artículo se enumeran los tipos que están obsoletos en .NET Framework 4.5 y .NET Framework 4.6, organizados por ensamblado. Utilice los vínculos siguientes para ver una lista de tipos obsoletos y las alternativas recomendadas en cada ensamblado. Dado que estos tipos están en desuso, todos sus miembros también lo están. Para obtener una lista de miembros obsoletos adicionales de la biblioteca de clases de .NET Framework, vea [Miembros obsoletos](obsolete-members.md).

- [Tipos obsoletos en ensamblados del sistema](#obsolete_types_in_system_assemblies)

  - [mscorlib.dll](#mscorlib)

  - [System.Core.dll](#Core)

  - [System.Data.dll](#data)

  - [System.Data.OracleClient.dll](#oracleclient)

  - [System.Design.dll](#design)

  - [System.dll](#system)

  - [System.EnterpriseServices.dll](#enterpriseservices)

  - [System.Net.dll](#net)

  - [System.ServiceModel.dll](#servicemodel)

  - [System.Web.dll](#web)

  - [System.Web.Mobile.dll](#mobile)

  - [System.Workflow.Activities.dll](#workflow_activities)

  - [System.Workflow.ComponentModel.dll](#workflow_componentmodel)

  - [System.Workflow.Runtime.dll](#workflow_runtime)

  - [System.WorkflowServices.dll](#workflowservices)

  - [System.Xaml.dll](#xaml)

  - [System.Xml.dll](#xml)

  - [WindowsBase.dll](#WindowsBase)

- [Tipos obsoletos en ensamblados de Microsoft](#obsolete_types_in_microsoft_assemblies)

  - [IEHost.dll e IEExec.exe](#IEHost)

  - [Microsoft.Build.Engine.dll](#Engine)

  - [Microsoft.JScript.dll](#jscript)

  - [Microsoft.VisualBasic.Compatibility.dll](#VBCompat)

  - [Microsoft.VisualBasic.Compatibility.Data.dll](#VBCompatData)

  - [Microsoft.VisualC.dll](#visualc)

<a name="obsolete_types_in_system_assemblies"></a>

## <a name="obsolete-types-in-system-assemblies"></a>Tipos obsoletos en ensamblados del sistema

En las tablas siguientes se enumeran los tipos que se han declarado obsoletos en ensamblados del sistema. Estos ensamblados se usan para el desarrollo de aplicaciones de uso\-general cuyo destino es .NET Framework.

<a name="mscorlib"></a>

### <a name="assembly-mscorlibdll"></a>Ensamblado: mscorlib.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.ExecutionEngineException?displayProperty=nameWithType>|Este tipo indicaba anteriormente un error irrecuperable no especificado en el runtime. El runtime ya no produce esta excepción, por lo que este tipo queda obsoleto.|
|<xref:System.Collections.CaseInsensitiveHashCodeProvider?displayProperty=nameWithType>|Use <xref:System.StringComparer?displayProperty=nameWithType> en su lugar.|
|<xref:System.Collections.IHashCodeProvider?displayProperty=nameWithType>|Use <xref:System.Collections.IEqualityComparer?displayProperty=nameWithType> en su lugar.|
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType>|La clase <xref:System.Configuration.Assemblies.AssemblyHash> está desusada.|
|<xref:System.Diagnostics.Contracts.Internal.ContractHelper?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5. Use la clase <xref:System.Runtime.CompilerServices.ContractHelper?displayProperty=nameWithType> del espacio de nombres System.Runtime.CompilerServices en su lugar.|
|<xref:System.Reflection.Emit.UnmanagedMarshal?displayProperty=nameWithType>|Hay una API alternativa disponible: emita el atributo personalizado <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.BIND_OPTS?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.BIND_OPTS?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.BINDPTR?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.BINDPTR?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.CALLCONV?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.CALLCONV?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.CONNECTDATA?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.CONNECTDATA?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.DESCKIND?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.DESCKIND?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.DISPPARAMS?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.DISPPARAMS?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.ELEMDESC?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.ELEMDESC?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.EXCEPINFO?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.EXCEPINFO?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.FILETIME?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.FILETIME?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.FUNCDESC?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.FUNCDESC?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.FUNCFLAGS?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.FUNCFLAGS?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.FUNCKIND?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.FUNCKIND?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=nameWithType>|Este atributo está en desuso y se quitará en futuras versiones.|
|<xref:System.Runtime.InteropServices.IDispatchImplType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=nameWithType> está desusado.|
|<xref:System.Runtime.InteropServices.IDLDESC?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IDLDESC?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.IDLFLAG?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IDLFLAG?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.IMPLTYPEFLAGS?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IMPLTYPEFLAGS?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.INVOKEKIND?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.INVOKEKIND?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.LIBFLAGS?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.LIBFLAGS?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.PARAMDESC?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.PARAMDESC?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.PARAMFLAG?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.PARAMFLAG?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.SetWin32ContextInIDispatchAttribute?displayProperty=nameWithType>|Este atributo está obsoleto. Los dominios de aplicación ya no tienen en cuenta los límites del contexto de activación en las llamadas de IDispatch.|
|<xref:System.Runtime.InteropServices.STATSTG?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.STATSTG?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.SYSKIND?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.SYSKIND?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.TYPEATTR?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.TYPEATTR?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.TYPEDESC?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.TYPEDESC?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.TYPEFLAGS?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.TYPEFLAGS?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.TYPEKIND?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.TYPEKIND?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.TYPELIBATTR?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.TYPELIBATTR?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMIBindCtx?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IBindCtx?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMIConnectionPoint?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMIConnectionPointContainer?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMIEnumConnectionPoints?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IEnumConnectionPoints?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMIEnumConnections?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IEnumConnections?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMIEnumMoniker?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IEnumMoniker?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMIEnumString?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IEnumString?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMIEnumVARIANT?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMIMoniker?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IMoniker?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMIPersistFile?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IPersistFile?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMIRunningObjectTable?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IRunningObjectTable?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMIStream?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMITypeComp?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.ITypeComp?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMITypeInfo?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.UCOMITypeLib?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.ITypeLib?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.VARDESC?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.VARDESC?displayProperty=nameWithType> en su lugar.|
|<xref:System.Runtime.InteropServices.VARFLAGS?displayProperty=nameWithType>|Utilice <xref:System.Runtime.InteropServices.ComTypes.VARFLAGS?displayProperty=nameWithType> en su lugar.|
|<xref:System.Security.SecurityCriticalScope?displayProperty=nameWithType>|<xref:System.Security.SecurityCriticalScope> solo se utiliza para la compatibilidad de transparencia con .NET 2.0.|
|<xref:System.Security.SecurityTreatAsSafeAttribute?displayProperty=nameWithType>|<xref:System.Security.SecurityTreatAsSafeAttribute> solo se utiliza para la compatibilidad de transparencia con .NET 2.0. Utilice <xref:System.Security.SecuritySafeCriticalAttribute?displayProperty=nameWithType> en su lugar.|
|<xref:System.Security.Policy.FirstMatchCodeGroup?displayProperty=nameWithType>|Este tipo está obsoleto y se quitará en futuras versiones de .NET Framework.|
|<xref:System.Security.Policy.PermissionRequestEvidence?displayProperty=nameWithType>|La seguridad declarativa de nivel de ensamblado está obsoleta y CLR ya no la exige de manera predeterminada.|
|<xref:System.Security.Policy.UnionCodeGroup?displayProperty=nameWithType>|Este tipo está obsoleto y se quitará en futuras versiones de .NET Framework.|

[Volver al principio](#introduction)

<a name="Core"></a>

### <a name="assembly-systemcoredll"></a>Ensamblado: System.Core.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.Runtime.CompilerServices.ExecutionScope?displayProperty=nameWithType>|El uso de este tipo genera un error del compilador.<br /><br /> No use este tipo.|

[Volver al principio](#introduction)

<a name="data"></a>

### <a name="assembly-systemdatadll"></a>Ensamblado: System.Data.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.Data.DataSysDescriptionAttribute?displayProperty=nameWithType>|<xref:System.Data.DataSysDescriptionAttribute> está desusado.|
|<xref:System.Data.PropertyAttributes?displayProperty=nameWithType>|<xref:System.Data.PropertyAttributes> está desusado.|
|<xref:System.Data.TypedDataSetGenerator?displayProperty=nameWithType>|La clase <xref:System.Data.TypedDataSetGenerator> se quitará en futuras versiones. Utilice <xref:System.Data.Design.TypedDataSetGenerator?displayProperty=nameWithType> en System.Design.dll.|
|<xref:System.Xml.XmlDataDocument?displayProperty=nameWithType>|La clase <xref:System.Xml.XmlDataDocument> se quitará en futuras versiones.|

[Volver al principio](#introduction)

<a name="oracleclient"></a>

### <a name="assembly-systemdataoracleclientdll"></a>Ensamblado: System.Data.OracleClient.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.Data.OracleClient.OracleClientFactory?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleClientFactory> está desusado.|
|<xref:System.Data.OracleClient.OracleCommand?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleCommand> está desusado.|
|<xref:System.Data.OracleClient.OracleCommandBuilder?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleCommandBuilder> está desusado.|
|<xref:System.Data.OracleClient.OracleConnection?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleConnection> está desusado.|
|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder> está desusado.|
|<xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleDataAdapter> está desusado.|
|<xref:System.Data.OracleClient.OraclePermission?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OraclePermission> está desusado.|
|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=nameWithType> está desusado.|

[Volver al principio](#introduction)

<a name="design"></a>

### <a name="assembly-systemdesigndll"></a>Ensamblado: System.Design.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.ComponentModel.Design.LocalizationExtenderProvider?displayProperty=nameWithType>|Esta clase está desusada. Utilice <xref:System.ComponentModel.Design.Serialization.CodeDomLocalizationProvider?displayProperty=nameWithType> en su lugar.|
|<xref:System.Web.UI.Design.DataBindingCollectionConverter?displayProperty=nameWithType>|No se recomienda el uso de este tipo porque la edición de DataBindings se inicia mediante <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=nameWithType> en lugar de la cuadrícula de propiedades.|
|<xref:System.Web.UI.Design.DataBindingCollectionEditor?displayProperty=nameWithType>|No se recomienda el uso de este tipo porque la edición de DataBindings se inicia mediante <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=nameWithType> en lugar de la cuadrícula de propiedades.|
|<xref:System.Web.UI.Design.IControlDesignerBehavior?displayProperty=nameWithType>|La alternativa recomendada es <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=nameWithType> y <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.IHtmlControlDesignerBehavior?displayProperty=nameWithType>|La alternativa recomendada es <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=nameWithType> y <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.ITemplateEditingFrame?displayProperty=nameWithType>|No se recomienda el uso de este tipo porque la edición de plantillas se controla en <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>. Para admitir la edición de plantillas, exponga los datos de la plantilla en la propiedad <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> y llame al método <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.IWebFormReferenceManager?displayProperty=nameWithType>|La alternativa recomendada es <xref:System.Web.UI.Design.WebFormsReferenceManager?displayProperty=nameWithType>. <xref:System.Web.UI.Design.WebFormsReferenceManager> contiene funcionalidad adicional y permite más extensibilidad. Para obtener <xref:System.Web.UI.Design.WebFormsReferenceManager>, utilice la propiedad `RootDesigner.ReferenceManager` de <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.IWebFormsDocumentService?displayProperty=nameWithType>|La alternativa recomendada es <xref:System.Web.UI.Design.WebFormsRootDesigner?displayProperty=nameWithType>. <xref:System.Web.UI.Design.WebFormsRootDesigner> contiene funcionalidad adicional y permite más extensibilidad. Para obtener <xref:System.Web.UI.Design.WebFormsRootDesigner>, utilice la propiedad <xref:System.Web.UI.Design.ControlDesigner.RootDesigner%2A> de <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.ITemplateEditingService?displayProperty=nameWithType>|No se recomienda el uso de este tipo porque la edición de plantillas se controla en <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>. Para admitir la edición de plantillas, exponga los datos de la plantilla en la propiedad <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> y llame al método <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.ReadWriteControlDesigner?displayProperty=nameWithType>|La alternativa recomendada es <xref:System.Web.UI.Design.ContainerControlDesigner?displayProperty=nameWithType> porque utiliza un objeto <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=nameWithType> para editar el contenido. Las regiones del diseñador permiten un control mejor del contenido que se va a editar.|
|<xref:System.Web.UI.Design.TemplateEditingService?displayProperty=nameWithType>|No se recomienda el uso de este tipo porque la edición de plantillas se controla en <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>. Para admitir la edición de plantillas, exponga los datos de la plantilla en la propiedad <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> y llame al método <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.TemplateEditingVerb?displayProperty=nameWithType>|No se recomienda el uso de este tipo porque la edición de plantillas se controla en <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>. Para admitir la edición de plantillas, exponga los datos de la plantilla en la propiedad <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType> y llame al método <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.WebControls.CalendarAutoFormatDialog?displayProperty=nameWithType>|No se recomienda el uso de este tipo porque el host del diseñador inicia el cuadro de diálogo Autoformato. La lista de autoformatos disponibles se expone en el objeto <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> en la propiedad <xref:System.Web.UI.Design.ControlDesigner.AutoFormats%2A?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.WebControls.PanelDesigner?displayProperty=nameWithType>|La alternativa recomendada es <xref:System.Web.UI.Design.WebControls.PanelContainerDesigner?displayProperty=nameWithType> porque utiliza un objeto <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=nameWithType> para editar el contenido. Las regiones del diseñador permiten un control mejor del contenido que se va a editar.|

[Volver al principio](#introduction)

<a name="system"></a>

### <a name="assembly-systemdll"></a>Ensamblado: System.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.ComponentModel.IComNativeDescriptorHandler?displayProperty=nameWithType>|Esta interfaz está en desuso. En su lugar, agregue un objeto <xref:System.ComponentModel.TypeDescriptionProvider?displayProperty=nameWithType> para controlar el tipo <xref:System.ComponentModel.TypeDescriptor.ComObjectType%2A?displayProperty=nameWithType>.|
|<xref:System.ComponentModel.RecommendedAsConfigurableAttribute?displayProperty=nameWithType>|Utilice <xref:System.ComponentModel.SettingsBindableAttribute?displayProperty=nameWithType> en su lugar para trabajar con el nuevo modelo de configuración.|
|<xref:System.ComponentModel.Design.Serialization.RootDesignerSerializerAttribute?displayProperty=nameWithType>|Este atributo está obsoleto. Utilice <xref:System.ComponentModel.Design.Serialization.DesignerSerializerAttribute?displayProperty=nameWithType> en su lugar.|
|<xref:System.Diagnostics.DiagnosticsConfigurationHandler?displayProperty=nameWithType>|Esta clase está desusada.|
|<xref:System.Diagnostics.PerformanceCounterManager?displayProperty=nameWithType>|Esta clase está desusada. Utilice los contadores de rendimiento a través de la clase <xref:System.Diagnostics.PerformanceCounter?displayProperty=nameWithType> en su lugar.|
|<xref:System.Net.GlobalProxySelection?displayProperty=nameWithType>|Esta clase está desusada. Utilice <xref:System.Net.WebRequest.DefaultWebProxy%2A?displayProperty=nameWithType> en su lugar para obtener acceso al proxy global predeterminado y establecerlo. Use "null" en lugar de <xref:System.Net.GlobalProxySelection.GetEmptyWebProxy%2A?displayProperty=nameWithType>.|
|<xref:System.Net.Sockets.SocketClientAccessPolicyProtocol?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|

[Volver al principio](#introduction)

<a name="enterpriseservices"></a>

### <a name="assembly-systementerpriseservicesdll"></a>Ensamblado: System.EnterpriseServices.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.EnterpriseServices.RegistrationHelperTx?displayProperty=nameWithType>|La clase <xref:System.EnterpriseServices.RegistrationHelperTx> está desusada.|

[Volver al principio](#introduction)

<a name="net"></a>

### <a name="assembly-systemnetdll"></a>Ensamblado: System.Net.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.Net.INetworkProgress?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|
|<xref:System.Net.IUnsafeWebRequestCreate?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|
|<xref:System.Net.NetworkProgressChangedEventArgs?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|
|<xref:System.Net.UiSynchronizationContext?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|
|<xref:System.Net.Sockets.HttpPolicyDownloaderProtocol?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|
|<xref:System.Net.Sockets.SecurityCriticalAction?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|
|<xref:System.Net.Sockets.SocketPolicy?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|
|<xref:System.Net.Sockets.UdpAnySourceMulticastClient?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|
|<xref:System.Net.Sockets.UdpSingleSourceMulticastClient?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|

[Volver al principio](#introduction)

<a name="servicemodel"></a>

### <a name="assembly-systemservicemodeldll"></a>Ensamblado: System.ServiceModel.Channels.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.ServiceModel.NetPeerTcpBinding?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|
|<xref:System.ServiceModel.Channels.HttpCookieContainerBindingElement?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Este tipo está obsoleto. Para habilitar el objeto <xref:System.Net.CookieContainer> de HTTP, utilice la propiedad `AllowCookies` del enlace HTTP o del objeto <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.|
|<xref:System.ServiceModel.Channels.PeerCustomResolverBindingElement?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|
|<xref:System.ServiceModel.Channels.PeerTransportBindingElement?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingCollectionElement?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|
|<xref:System.ServiceModel.Configuration.PeerTransportElement?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|
|<xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> La característica de canal del mismo nivel está obsoleta y se quitará en el futuro.|

[Volver al principio](#introduction)

<a name="web"></a>

### <a name="assembly-systemwebdll"></a>Ensamblado: System.Web.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.Web.Configuration.PassportAuthentication?displayProperty=nameWithType>|Este tipo está obsoleto. El producto de autenticación mediante Passport ya no se admite y se ha sustituido por la [cuenta Microsoft](https://account.microsoft.com/account/Account?destrt=home-index).|
|<xref:System.Web.Mail.MailAttachment?displayProperty=nameWithType>|La alternativa recomendada es <xref:System.Net.Mail.Attachment?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailEncoding?displayProperty=nameWithType>|La alternativa recomendada es <xref:System.Net.Mime.TransferEncoding?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailFormat?displayProperty=nameWithType>|La alternativa recomendada es <xref:System.Net.Mail.MailMessage.IsBodyHtml%2A?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailMessage?displayProperty=nameWithType>|La alternativa recomendada es <xref:System.Net.Mail.MailMessage?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailPriority?displayProperty=nameWithType>|La alternativa recomendada es <xref:System.Net.Mail.MailPriority?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.SmtpMail?displayProperty=nameWithType>|La alternativa recomendada es <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>.|
|<xref:System.Web.Security.PassportAuthenticationEventArgs?displayProperty=nameWithType>|Este tipo está obsoleto. El producto de autenticación mediante Passport ya no se admite y se ha sustituido por la [cuenta Microsoft](https://account.microsoft.com/account/Account?destrt=home-index).|
|<xref:System.Web.Security.PassportAuthenticationEventHandler?displayProperty=nameWithType>|Este tipo está obsoleto. El producto de autenticación mediante Passport ya no se admite y se ha sustituido por la [cuenta Microsoft](https://account.microsoft.com/account/Account?destrt=home-index).|
|<xref:System.Web.Security.PassportAuthenticationModule?displayProperty=nameWithType>|Este tipo está obsoleto. El producto de autenticación mediante Passport ya no se admite y se ha sustituido por la [cuenta Microsoft](https://account.microsoft.com/account/Account?destrt=home-index).|
|<xref:System.Web.Security.PassportIdentity?displayProperty=nameWithType>|Este tipo está obsoleto. El producto de autenticación mediante Passport ya no se admite y se ha sustituido por la [cuenta Microsoft](https://account.microsoft.com/account/Account?destrt=home-index).|
|<xref:System.Web.Security.PassportPrincipal?displayProperty=nameWithType>|Este tipo está obsoleto. El producto de autenticación mediante Passport ya no se admite y se ha sustituido por la [cuenta Microsoft](https://account.microsoft.com/account/Account?destrt=home-index).|
|<xref:System.Web.UI.ObjectConverter?displayProperty=nameWithType>|La alternativa recomendada es <xref:System.Convert?displayProperty=nameWithType> y <xref:System.String.Format%2A?displayProperty=nameWithType>.|

[Volver al principio](#introduction)

<a name="mobile"></a>

### <a name="assembly-systemwebmobiledll"></a>Ensamblado: System.Web.Mobile.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.Web.Mobile.CookielessData?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.DeviceFilterElement?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.DeviceFilterElementCollection?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.DeviceFiltersSection?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.ErrorHandlerModule?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileCapabilities?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileDeviceCapabilitiesSectionHandler?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileErrorInfo?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileFormsAuthentication?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.IMobileDesigner?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.IMobileWebFormServices?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.MobileResource?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.Converters.DataFieldConverter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.Converters.DataMemberConverter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.AdRotator?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Alignment?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ArrayListCollectionBase?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.BaseValidator?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.BooleanOption?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Calendar?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Command?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.CommandFormat?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.CompareValidator?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Constants?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ControlElement?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ControlElementCollection?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ControlPager?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.CustomValidator?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DesignerAdapterAttribute?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceElement?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceElementCollection?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceOverridableAttribute?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecific?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoice?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceCollection?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceControlBuilder?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateBuilder?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateContainer?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificControlBuilder?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ErrorFormatterPage?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FontInfo?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FontSize?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Form?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FormControlBuilder?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FormMethod?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.IControlAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Image?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.IObjectListFieldCollection?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.IPageAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ItemPager?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ITemplateable?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Label?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Link?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.List?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListCommandEventArgs?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListCommandEventHandler?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListControlBuilder?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListDataBindEventArgs?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListDataBindEventHandler?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListDecoration?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListSelectType?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralLink?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralText?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralTextContainerControlBuilder?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralTextControlBuilder?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LoadItemsEventArgs?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LoadItemsEventHandler?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControl?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControlBuilder?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControlsSection?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControlsSectionHandler?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileListItem?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileListItemCollection?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileListItemType?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobilePage?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileTypeNameConverter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileUserControl?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectList?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommand?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommandCollection?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventArgs?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventHandler?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListControlBuilder?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventArgs?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventHandler?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListField?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListFieldCollection?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListItem?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListItemCollection?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventArgs?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventHandler?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventArgs?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventHandler?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListTitleAttribute?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListViewMode?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PagedControl?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PagerStyle?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Panel?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PanelControlBuilder?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PersistNameAttribute?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PhoneCall?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.RangeValidator?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.RegularExpressionValidator?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.RequiredFieldValidator?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.SelectionList?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Style?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.StyleSheet?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.StyleSheetControlBuilder?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TemplateContainer?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextBox?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextBoxControlBuilder?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextControl?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextView?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextViewElement?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ValidationSummary?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Wrapping?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCalendarAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCommandAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlFormAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlImageAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlLinkAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlMobileTextWriter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPageAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPhoneCallAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlSelectionListAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlTextBoxAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ControlAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCalendarAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCommandAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlControlAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlFormAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlImageAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLabelAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLinkAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlListAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLiteralTextAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlMobileTextWriter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlObjectListAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPageAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPanelAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPhoneCallAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlSelectionListAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextBoxAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextViewAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidationSummaryAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidatorAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.MobileTextWriter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.MultiPartWriter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlMobileTextWriter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlPageAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlCalendarAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlCommandAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlControlAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlFormAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlImageAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlLabelAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlLinkAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlListAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlLiteralTextAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlMobileTextWriter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlObjectListAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPageAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPanelAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPhoneCallAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPostFieldType?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlSelectionListAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextBoxAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextViewAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidationSummaryAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidatorAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.Doctype?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.StyleSheetLocation?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCalendarAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCommandAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlControlAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCssHandler?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlFormAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlImageAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLabelAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLinkAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlListAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLiteralTextAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlMobileTextWriter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlObjectListAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPageAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPanelAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPhoneCallAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlSelectionListAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextBoxAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextViewAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidationSummaryAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidatorAdapter?displayProperty=nameWithType>|El ensamblado System.Web.Mobile.dll ha quedado en desuso y no se debe utilizar. Para obtener información sobre cómo desarrollar aplicaciones móviles de ASP.NET, vea [ASP.NET para dispositivos móviles](/aspnet/mobile/overview).|

[Volver al principio](#introduction)

<a name="workflow_activities"></a>

### <a name="assembly-systemworkflowactivitiesdll"></a>Ensamblado: System.Workflow.Activities.dll

|Tipo|Mensaje|
|----------|-------------|
|Todos los tipos del espacio de nombres <xref:System.Workflow.Activities?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Configuration.ActiveDirectoryRoleFactoryConfiguration?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Rules.RuleActionTrackingEvent?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Rules.RuleConditionReference?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Rules.RuleSetReference?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|

[Volver al principio](#introduction)

<a name="workflow_componentmodel"></a>

### <a name="assembly-systemworkflowcomponentmodeldll"></a>Ensamblado: System.Workflow.ComponentModel.dll

|Tipo|Mensaje|
|----------|-------------|
|Todos los tipos del espacio de nombres <xref:System.Workflow.ComponentModel> excepto <xref:System.Workflow.ComponentModel.GetValueOverride?displayProperty=nameWithType> y <xref:System.Workflow.ComponentModel.SetValueOverride?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|Todos los tipos del espacio de nombres <xref:System.Workflow.ComponentModel.Compiler> excepto <xref:System.Workflow.ComponentModel.Compiler.ValidationError?displayProperty=nameWithType> y <xref:System.Workflow.ComponentModel.Compiler.ValidationErrorCollection?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|Todos los tipos del espacio de nombres <xref:System.Workflow.ComponentModel.Design> excepto <xref:System.Workflow.ComponentModel.Design.ConnectorEventHandler>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializationManager?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializer?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityMarkupSerializer?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivitySurrogateSelector?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityTypeCodeDomSerializer?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.CompositeActivityMarkupSerializer?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.DependencyObjectCodeDomSerializer?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|

[Volver al principio](#introduction)

<a name="workflow_runtime"></a>

### <a name="assembly-systemworkflowruntimedll"></a>Ensamblado: System.Workflow.Runtime.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.Activities.Statements.Interop?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br />Los tipos de Workflow Foundation 3.0 están desusados. En su lugar, use los tipos de Workflow 4.0 de <xref:System.Activities>\*.|
|<xref:System.Activities.Tracking.InteropTrackingRecord?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br />Los tipos de Workflow Foundation 3.0 están desusados. En su lugar, use los tipos de Workflow 4.0 de <xref:System.Activities>\*.|
|Todos los tipos del espacio de nombres <xref:System.Workflow.Runtime>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|Todos los tipos del espacio de nombres <xref:System.Workflow.Runtime.Configuration>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|Todos los tipos del espacio de nombres <xref:System.Workflow.Runtime.DebugEngine> excepto <xref:System.Workflow.Runtime.DebugEngine.DebugEngineCallback>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|Todos los tipos del espacio de nombres <xref:System.Workflow.Runtime.Hosting> excepto <xref:System.Workflow.Runtime.Hosting.WorkflowCommitWorkBatchService.CommitWorkBatchCallback>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|
|Todos los tipos del espacio de nombres <xref:System.Workflow.Runtime.Tracking>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de System.Workflow.\* están en desuso. En su lugar, use los nuevos tipos de <xref:System.Activities>\*.|

[Volver al principio](#introduction)

<a name="workflowservices"></a>

### <a name="assembly-systemworkflowservicesdll"></a>Ensamblado: System.WorkflowServices.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.ServiceModel.WorkflowServiceHost?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Activation.WorkflowServiceHostFactory?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Activities.Description.WorkflowRuntimeEndpoint?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Configuration.ExtendedWorkflowRuntimeServiceElementCollection?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Configuration.PersistenceProviderElement?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Configuration.WorkflowRuntimeElement?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.DurableOperationAttribute?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.DurableServiceAttribute?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.PersistenceProviderBehavior?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.UnknownExceptionAction?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.WorkflowRuntimeBehavior?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Dispatcher.DurableOperationContext?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.InstanceLockException?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.InstanceNotFoundException?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.LockingPersistenceProvider?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.PersistenceException?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.PersistenceProvider?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.PersistenceProviderFactory?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.SqlPersistenceProviderFactory?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|Todos los tipos del espacio de nombres <xref:System.Workflow.Activities?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|
|<xref:System.Workflow.Runtime.Hosting.ChannelManagerService?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> Los tipos de WF 3 están en desuso. En su lugar, use los nuevos tipos de WF 4 de <xref:System.Activities>\*.|

[Volver al principio](#introduction)

<a name="xaml"></a>

### <a name="assembly-systemxamldll"></a>Ensamblado: System.Xaml.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute?displayProperty=nameWithType>|Este tipo no lo utiliza el analizador de XAML. Consulte <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute?displayProperty=nameWithType>.|

[Volver al principio](#introduction)

<a name="xml"></a>

### <a name="assembly-systemxmldll"></a>Ensamblado: System.Xml.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.Xml.IApplicationResourceStreamResolver?displayProperty=nameWithType>|Quedó por vez primera en desuso en .NET Framework 4.5.<br /><br /> El uso de este tipo genera un error del compilador.<br /><br /> Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|
|<xref:System.Xml.Schema.XmlSchemaCollection?displayProperty=nameWithType>|Use <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> para la compilación y validación de esquema.|
|<xref:System.Xml.XmlValidatingReader?displayProperty=nameWithType>|Utilice un objeto <xref:System.Xml.XmlReader?displayProperty=nameWithType> creado por el método <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType> que utilice en su lugar el objeto <xref:System.Xml.XmlReaderSettings?displayProperty=nameWithType> apropiado.|
|<xref:System.Xml.XmlXapResolver?displayProperty=nameWithType>|El uso de este tipo genera un error del compilador. Esta API es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.|
|<xref:System.Xml.Xsl.XslTransform?displayProperty=nameWithType>|Esta clase está desusada. Use <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType> en su lugar.|

[Volver al principio](#introduction)

<a name="WindowsBase"></a>

### <a name="assembly-windowsbasedll"></a>Ensamblado: WindowsBase.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=nameWithType>|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=nameWithType> está desusado. Esta interfaz ya no se utiliza.|

[Volver al principio](#introduction)

<a name="obsolete_types_in_microsoft_assemblies"></a>

## <a name="obsolete-types-in-microsoft-assemblies"></a>Tipos obsoletos en ensamblados de Microsoft

En las secciones siguientes se enumeran los tipos obsoletos en ensamblados de Microsoft. Estos ensamblados son ensamblados para fines especiales, como ensamblados que están destinados a un lenguaje individual (por ejemplo, Microsoft.JScript.dll o Microsoft.VisualC.dll).

<a name="IEHost"></a>

### <a name="assembly-iehostdll-and-ieexecexe"></a>Ensamblado: IEHost.dll e IEExec.exe

Se han quitado de .NET Framework los ensamblados IEHost.dll e IEExec.exe. Todos sus tipos y miembros están obsoletos y no se admiten a partir de .NET Framework 4. Estos ensamblados se utilizaban para hospedar los controles de Windows Forms y ejecutar las aplicaciones ejecutables en Internet Explorer. Entre las alternativas recomendadas se incluye ClickOnce, aplicaciones de explorador XAML (XBAP) y Microsoft Silverlight.

[Volver al principio](#introduction)

<a name="Engine"></a>

### <a name="assembly-microsoftbuildenginedll"></a>Ensamblado: Microsoft.Build.Engine.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:Microsoft.Build.BuildEngine.Engine?displayProperty=nameWithType>|Esta clase está desusada. Use <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=nameWithType> del ensamblado *Microsoft.Build* en su lugar.|
|<xref:Microsoft.Build.BuildEngine.Project?displayProperty=nameWithType>|Esta clase está desusada. Use <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=nameWithType> del ensamblado *Microsoft.Build* en su lugar.|

[Volver al principio](#introduction)

<a name="jscript"></a>

### <a name="assembly-microsoftjscriptdll"></a>Ensamblado: Microsoft.JScript.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:Microsoft.JScript.Vsa.BaseVsaEngine?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.BaseVsaSite?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.BaseVsaStartup?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.IJSVsaCodeItem?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.IJSVsaEngine?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.IJSVsaError?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.IJSVsaGlobalItem?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.IJSVsaItem?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.IJSVsaItems?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.IJSVsaPersistSite?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.IJSVsaReferenceItem?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.IJSVsaSite?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.JSVsaError?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.JSVsaException?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.JSVsaItemFlag?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.JSVsaItemType?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.ResInfo?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|
|<xref:Microsoft.JScript.Vsa.VsaEngine?displayProperty=nameWithType>|Este tipo ha quedado en desuso en Visual Studio 2005 y esta característica no se ha reemplazado. Vea la documentación de <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType> para obtener información adicional.|

[Volver al principio](#introduction)

<a name="VBCompat"></a>

### <a name="assembly-microsoftvisualbasiccompatibilitydll"></a>Ensamblado: Microsoft.VisualBasic.Compatibility.dll

Para más información sobre la migración desde Visual Basic 6, vea [Centro de recursos de Visual Basic 6.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-basic-6/visual-basic-6.0-documentation).

|Tipo|Mensaje|
|----------|-------------|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseControlArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseOcxArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ButtonArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckBoxArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckedListBoxArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ColorDialogArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ComboBoxArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBox?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBoxArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBox?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBoxArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBox?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBoxArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FixedLengthString?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FontDialogArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FormShowConstants?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.GroupBoxArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.HScrollBarArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ImageListArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LabelArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxItem?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListViewArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LoadResConstants?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MaskedTextBoxArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MenuItemArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MouseButtonConstants?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.OpenFileDialogArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PanelArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PictureBoxArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PrintDialogArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ProgressBarArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RadioButtonArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RichTextBoxArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SaveFileDialogArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ScaleMode?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ShiftConstants?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusBarArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusStripArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.Support?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TabControlArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TextBoxArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TimerArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolBarArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripMenuItemArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TreeViewArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.VScrollBarArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebBrowserArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClass?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassContainingClassNotOptional?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassCouldNotFindEvent?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemCannotBeCurrentWebItem?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemRespondNotFound?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassUserWebClassNameNotOptional?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebClassFileNameNotOptional?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebItemNotValid?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItem?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemAssociatedWebClassNotOptional?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemClosingTagNotFound?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadEmbeddedResource?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadTemplateFile?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNameNotOptional?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNoTemplateSpecified?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemTooManyNestedTags?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemUnexpectedErrorReadingTemplateFile?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ZOrderConstants?displayProperty=nameWithType>|Este miembro está obsoleto.|

[Volver al principio](#introduction)

<a name="VBCompatData"></a>

### <a name="assembly-microsoftvisualbasiccompatibilitydatadll"></a>Ensamblado: Microsoft.VisualBasic.Compatibility.Data.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.BOFActionEnum?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EndOfRecordsetDelegate?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EOFActionEnum?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.ErrorDelegate?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchCompleteDelegate?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchProgressDelegate?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FieldChangeCompleteDelegate?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.MoveCompleteDelegate?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.OrientationEnum?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordChangeCompleteDelegate?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordsetChangeCompleteDelegate?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeFieldDelegate?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordDelegate?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordsetDelegate?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillMoveDelegate?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODCArray?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseDataEnvironment?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BindingCollectionEnumerator?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CONNECTDATA?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBBINDING?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBCOLUMNINFO?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBID?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBinding?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBindingCollection?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBKINDENUM?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBPROPIDSET?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IAccessor?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IChapteredRowset?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IColumnsInfo?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPoint?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPointContainer?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormat?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormatDisp?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnectionPoints?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnections?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPosition?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPositionChange?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowset?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetChange?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetIdentity?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetInfo?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetNotify?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBinding?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBindingCollection?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SRDescriptionAttribute?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UGUID?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UNAME?displayProperty=nameWithType>|Este miembro está obsoleto.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UpdateMode?displayProperty=nameWithType>|Este miembro está obsoleto.|

[Volver al principio](#introduction)

<a name="visualc"></a>

### <a name="assembly-microsoftvisualcdll"></a>Ensamblado: Microsoft.VisualC.dll

|Tipo|Mensaje|
|----------|-------------|
|<xref:Microsoft.VisualC.DebugInfoInPDBAttribute?displayProperty=nameWithType>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|
|<xref:Microsoft.VisualC.DecoratedNameAttribute?displayProperty=nameWithType>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|
|<xref:Microsoft.VisualC.IsConstModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|
|<xref:Microsoft.VisualC.IsCXXReferenceModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|
|<xref:Microsoft.VisualC.IsLongModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|
|<xref:Microsoft.VisualC.IsSignedModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|
|<xref:Microsoft.VisualC.IsVolatileModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|
|<xref:Microsoft.VisualC.MiscellaneousBitsAttribute?displayProperty=nameWithType>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|
|<xref:Microsoft.VisualC.NeedsCopyConstructorModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|
|<xref:Microsoft.VisualC.NoSignSpecifiedModifier?displayProperty=nameWithType>|Microsoft.VisualC.dll es un ensamblado obsoleto y solamente existe por compatibilidad con versiones anteriores.|

## <a name="see-also"></a>Vea también

- [Lo obsoleto en la biblioteca de clases](whats-obsolete.md)
- [Miembros obsoletos](obsolete-members.md)
