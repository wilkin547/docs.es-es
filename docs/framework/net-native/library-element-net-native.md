---
title: <Library>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc3c85ab99574c96d8a68d4221f218a1340e4122
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049645"
---
# <a name="library-element-net-native"></a>\<Elemento > de la biblioteca (.NET Native)
Define el ensamblado que contiene los tipos y miembros de tipo cuyos metadatos están disponibles para la reflexión en tiempo de ejecución.  
  
 Elemento \<Directives>  
Elemento \<Library>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`Name`|Atributo necesario. Especifica el nombre de un ensamblado. Los elementos secundarios de este elemento `<Library>` definen la directiva de reflexión en tiempo de ejecución para los tipos y miembros de tipos en este ensamblado.|  
  
## <a name="name-attribute"></a>Name (atributo)  
  
|Value|DESCRIPCIÓN|  
|-----------|-----------------|  
|*assembly_name*|Nombre simple del ensamblado sin la extensión de archivo. Este atributo corresponde a la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>. Por ejemplo, el nombre de un ensamblado denominado Extensions.dll es "Extensions". Vea la sección Comentarios para conocer una forma especial de *assembly_name* que admite la inclusión condicional de metadatos del ensamblado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<Assembly>](assembly-element-net-native.md)|Aplica la directiva a todos los tipos en un ensamblado determinado.|  
|[\<Namespace>](namespace-element-net-native.md)|Aplica la directiva a todos los tipos en un espacio de nombres determinado.|  
|[\<Type>](type-element-net-native.md)|Aplica la directiva a un tipo determinado, como una clase o una estructura.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Aplica la directiva a un tipo genérico construido. Por ejemplo, se podría usar un elemento [\<TypeInstantiation>](typeinstantiation-element-net-native.md) para definir la directiva para un tipo `List<String>`.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<Directives>](directives-element-net-native.md)|Elemento raíz de un archivo de directivas en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 El elemento [\<Directives>](directives-element-net-native.md) puede contener cero, uno o más elementos `<Library>`.  
  
 El elemento `<Library>` sirve de contenedor para definir los elementos de programa cuyos metadatos son necesarios en tiempo de ejecución. Este elemento no expresa la directiva. En tiempo de compilación, las herramientas del compilador buscan únicamente en la biblioteca designada por el elemento `<Library>` para encontrar los elementos de programa identificados por sus elementos secundarios. Por el contrario, las herramientas del compilador buscan en todas las bibliotecas (incluidas las bibliotecas principales de .NET Framework), para encontrar los elementos de programa identificados por los elementos secundarios del elemento [\<Application>](application-element-net-native.md).  
  
 Las directivas de `<Library>` se pueden usar de manera condicional. Si el nombre del `<Library>` elemento comienza y termina con un asterisco (\*), la `<Library>` directiva solo tiene efecto si la aplicación hace referencia al ensamblado especificado entre los asteriscos. Por ejemplo, la siguiente directiva en tiempo de ejecución solo se aplica si la aplicación hace referencia al ensamblado Utilities. dll.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a>Vea también

- [\<Application >, elemento](application-element-net-native.md)
- [\<Directivas > elemento](directives-element-net-native.md)
- [Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))](runtime-directives-rd-xml-configuration-file-reference.md)
- [Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)](runtime-directive-elements.md)
