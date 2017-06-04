---
title: "&lt;loadFromRemoteSources&gt; (elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "loadFromRemoteSources (elemento)"
  - "<loadFromRemoteSources> (elemento)"
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
caps.latest.revision: 31
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 31
---
# &lt;loadFromRemoteSources&gt; (elemento)
Especifica si se debe conceder plena confianza a los ensamblados de orígenes remotos.  
  
> [!NOTE]
>  Si le remitieron a este tema debido a un mensaje de error en la lista de errores de proyecto de Visual Studio o a un error de compilación, consulte [Cómo: Usar un ensamblado desde el web en Visual Studio](http://msdn.microsoft.com/es-es/d8635b63-89a0-41aa-90f4-f351b2111070).  
  
## Sintaxis  
  
```  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si se debe conceder plena confianza a un ensamblado que se carga desde orígenes remotos.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No conceda plena confianza a las aplicaciones de orígenes remotos.  Éste es el valor predeterminado.|  
|`true`|Conceda plena confianza a las aplicaciones de orígenes remotos.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## Comentarios  
 En .NET Framework versión 3.5 y en versiones anteriores, si cargaba un ensamblado desde una ubicación remota, el ensamblado se ejecutaba con confianza parcial con un conjunto de permisos que dependía de la zona en la que se cargara.  Por ejemplo, si se carga un ensamblado de un sitio Web, se cargan en la zona de Internet y concedió el conjunto de permisos internet.  Es decir, se ejecutaba en un espacio aislado de Internet.  Si intenta ejecutar ese ensamblado en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y las versiones posteriores, se produce una excepción; debe cualquiera crear explícitamente un espacio aislado para el ensamblado \(vea [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)\), o ejecútelo con plena confianza.  
  
 El elemento de `<loadFromRemoteSources>` permite especificar que los ensamblados que habrían ejecutado parcialmente de confianza en versiones anteriores de .NET Framework pueden ser de plena confianza ejecutado en [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y versiones posteriores.  De forma predeterminada, los ensamblados remotos no se ejecutan en [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y posterior.  Para ejecutar un ensamblado, le remotos debe cualquier ejecútelo como de plena confianza o crear <xref:System.AppDomain> en espacio aislado en las que ejecutarlo.  
  
> [!NOTE]
>  En [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], ejecutan a los ensamblados de recursos compartidos de red locales como de plena confianza de forma predeterminada; no tiene que habilitar el elemento de `<loadFromRemoteSources>` .  
  
> [!NOTE]
>  Si una aplicación ha copiado del web, es marca\/marcada por Windows como una aplicación Web, incluso si reside en el equipo local.  Puede cambiar esa designación cambiando las propiedades del archivo o puede usar el elemento `<loadFromRemoteSources>` para conceder plena confianza al ensamblado.  Como alternativa, puede utilizar el método de <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> para cargar un ensamblado local que el sistema operativo ha marcado como de carga de web.  
  
 El atributo `enabled` para este elemento es efectivo únicamente cuando la seguridad de acceso del código \(CAS\) está deshabilitada.  De forma predeterminada, la directiva de CAS está deshabilitada en [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y en versiones posteriores.  Si establece `enabled` en `true`, las aplicaciones remotas gozan de plena confianza.  
  
 Si `<loadFromRemoteSources>` `enabled` no se establece en `true`, se iniciará una excepción en las condiciones siguientes:  
  
-   El comportamiento del espacio aislado del dominio actual es distinto que su comportamiento en [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  En necesario deshabilitar la directiva de CAS y que el dominio actual no esté en un espacio aislado.  
  
-   El ensamblado que se está cargando no procede de la zona `MyComputer`.  
  
> [!NOTE]
>  Puede obtener una <xref:System.IO.FileLoadException> en una aplicación de Windows Virtual PC cuando intente cargar un archivo desde carpetas vinculadas en el equipo en que se hospeda.  Este error también puede aparecer si intenta cargar un archivo de una carpeta vinculada encima [Servicios de Escritorio remoto](http://go.microsoft.com/fwlink/?LinkId=182775) \(Terminal services\).  Para evitar la excepción, establezca `enabled` en `true`.  
  
 Al establecer el elemento `<loadFromRemoteSources>` en `true` se impide el inicio de esta excepción.  Le permite especificar que no está confiando en Common Language Runtime para crear un espacio aislado para los ensamblados cargados por seguridad y que se pueden ejecutar como de plena confianza.  
  
> [!IMPORTANT]
>  Si el ensamblado no se debe ejecutar como de plena confianza, no establezca este elemento de configuración.  En su lugar, cree un <xref:System.AppDomain> en un espacio aislado en el que cargar el ensamblado.  
  
## Archivo de configuración  
 Este elemento se utiliza normalmente en el archivo de configuración de la aplicación, pero se puede utilizar en otros archivos de configuración dependiendo del contexto.  Para obtener más información, vea el [Más Implícita utiliza de la Directiva CAS: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) artículo en el blog de seguridad de.NET.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo conceder plena confianza a las aplicaciones desde orígenes remotos.  
  
```  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Más Implícita utiliza de la Directiva CAS: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839)   
 [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)   
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)