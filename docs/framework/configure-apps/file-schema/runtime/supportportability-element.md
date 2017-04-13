---
title: "&lt;supportPortability&gt; (Elemento) | Microsoft Docs"
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
  - "<supportPortability> (elemento)"
  - "supportPortability (elemento)"
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# &lt;supportPortability&gt; (Elemento)
Especifica que una aplicación puede hacer referencia al mismo ensamblado en dos implementaciones diferentes de .NET Framework, deshabilitando el comportamiento predeterminado que trata los ensamblados como equivalentes para los propósitos de portabilidad de aplicación.  
  
## Sintaxis  
  
```  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|PKT|Atributo necesario.<br /><br /> Especifica el token de clave pública del ensamblado afectado, como una cadena.|  
|enabled|Atributo opcional.<br /><br /> Especifica si se debería habilitar el soporte para la portabilidad entre las implementaciones del ensamblado de .NET Framework especificado.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|true|Habilita el soporte para la portabilidad entre las implementaciones del ensamblado de .NET Framework especificado.  Éste es el valor predeterminado.|  
|false|Deshabilita el soporte para la portabilidad entre las implementaciones del ensamblado de .NET Framework especificado.  Esto permite a la aplicación tener referencias a varias implementaciones del ensamblado especificado.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
|`assemblyBinding`|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|  
  
## Comentarios  
 A partir de [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], se proporciona automáticamente compatibilidad para las aplicaciones que pueden usar cualquiera de las dos implementaciones de .NET Framework, por ejemplo, la implementación de .NET Framework o de .NET Framework para Silverlight.  El enlazador del ensamblado considera equivalentes las dos implementaciones de un ensamblado de .NET Framework determinado.  En algunos escenarios, esta característica de portabilidad de aplicación produce problemas.  En esos escenarios, se puede usar el elemento `<supportPortability>` para deshabilitar la característica.  
  
 Uno de estos escenarios es un ensamblado que tiene que hacer referencia al mismo tiempo a la implementación de .NET Framework y a la implementación de .NET Framework para Silverlight de un ensamblado de referencia determinado.  Por ejemplo, un diseñador de XAML escrito en Windows Presentation Foundation \(WPF\) podría tener que hacer referencia a la implementación del escritorio de WPF, para la interfaz de usuario del diseñador, y al subconjunto de WPF que se incluye en la implementación de Silverlight.  De forma predeterminada, las referencias independientes producen un error del compilador, ya que el enlace del ensamblado considera los dos ensamblados equivalentes.  Este elemento deshabilita el comportamiento predeterminado y permite que la compilación se realice correctamente.  
  
> [!IMPORTANT]
>  Para que el compilador pase la información a la lógica de enlace del ensamblado de Common Language Runtime, debe usar la opción de compilador `/appconfig` para especificar la ubicación del archivo app.config que contiene este elemento.  
  
## Ejemplo  
 El siguiente ejemplo permite a una aplicación tener referencias a la implementación de .NET Framework y de .NET Framework para Silverlight de cualquier ensamblado de .NET Framework que exista en ambas implementaciones.  Se debe usar la opción de compilador `/appconfig` para especificar la ubicación de este archivo app.config.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [\/appconfig \(Opciones del compilador de C\#\)](http://msdn.microsoft.com/library/ee523958.aspx)   
 [.NET Framework Assembly Unification Overview](http://msdn.microsoft.com/es-es/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)