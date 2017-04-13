---
title: "Elemento &lt;Library&gt; (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Elemento &lt;Library&gt; (.NET Native)
Define el ensamblado que contiene los tipos y miembros de tipo cuyos metadatos están disponibles para la reflexión en tiempo de ejecución.  
  
## Sintaxis  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`Name`|Atributo necesario.  Especifica el nombre de un ensamblado.  Los elementos secundarios de este elemento `<Library>` definen la directiva de reflexión en tiempo de ejecución para los tipos y miembros de tipos en este ensamblado.|  
  
## Name \(atributo\)  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*assembly\_name*|Nombre simple del ensamblado sin la extensión de archivo.  Este atributo corresponde a la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=fullName>.  Por ejemplo, el nombre de un ensamblado denominado Extensions.dll es "Extensions".  Consulte la sección Comentarios para ver una forma especial de *assembly\_name* que admite la inclusión condicional de metadatos del ensamblado.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<Assembly\>](../../../docs/framework/net-native/assembly-element-net-native.md)|Aplica la directiva a todos los tipos en un ensamblado determinado.|  
|[\<Namespace\>](../../../docs/framework/net-native/namespace-element-net-native.md)|Aplica la directiva a todos los tipos en un espacio de nombres determinado.|  
|[\<Type\>](../../../docs/framework/net-native/type-element-net-native.md)|Aplica la directiva a un tipo determinado, como una clase o una estructura.|  
|[\<TypeInstantiation\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Aplica la directiva a un tipo genérico construido.  Por ejemplo, se podría usar un elemento [\<TypeInstantiation\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) para definir la directiva para un tipo `List<String>`.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<Directives\>](../../../docs/framework/net-native/directives-element-net-native.md)|Elemento raíz de un archivo de directivas en tiempo de ejecución.|  
  
## Comentarios  
 El elemento [\<Directives\>](../../../docs/framework/net-native/directives-element-net-native.md) puede contener cero, uno o más elementos `<Library>`.  
  
 El elemento `<Library>` sirve de contenedor para definir los elementos de programa cuyos metadatos son necesarios en tiempo de ejecución. Este elemento no expresa la directiva.  En tiempo de compilación, las herramientas del compilador buscan únicamente en la biblioteca designada por el elemento `<Library>` para encontrar los elementos de programa identificados por sus elementos secundarios.  Por el contrario, las herramientas del compilador buscan en todas las bibliotecas \(incluidas las bibliotecas principales de .NET Framework\), para encontrar los elementos de programa identificados por los elementos secundarios del elemento [\<Application\>](../../../docs/framework/net-native/application-element-net-native.md).  
  
 Las directivas de `<Library>` se pueden usar de manera condicional.  Si el nombre del elemento `<Library>` empieza y termina con un asterisco \(\*\), la directiva `<Library>` tendrá efecto solo si la aplicación hace referencia al ensamblado especificado entre los asteriscos.  Por ejemplo, la siguiente directiva en tiempo de ejecución se aplica únicamente si la aplicación hace referencia al ensamblado Utillities.dll.  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name=”*Utilities*”>  
   ...  
  </Library>  
</Directives>  
  
```  
  
## Vea también  
 [Elemento \<Application\>](../../../docs/framework/net-native/application-element-net-native.md)   
 [Elemento \<Directives\>](../../../docs/framework/net-native/directives-element-net-native.md)   
 [Referencia del archivo de configuración de directivas en tiempo de ejecución \(rd.xml\)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Elementos de directivas en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-elements.md)