---
title: Elementos de directivas en tiempo de ejecución
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: c900516382c8e526a6b0021bb2b681486283f3ab
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128168"
---
# <a name="runtime-directive-elements"></a>Elementos de directivas en tiempo de ejecución
El formato del archivo de directivas de tiempo de ejecución (rd.xml) es compatible con los siguientes elementos de directiva de tiempo de ejecución. Vea [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)) para obtener una representación jerárquica.  
  
 [\<Application>](application-element-net-native.md)  
 Aplica la directiva de reflexión en tiempo de ejecución a todos los tipos utilizados por la aplicación y sirve como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión en tiempo de ejecución. Se trata de un elemento secundario del elemento [\<Directives>](directives-element-net-native.md).  
  
 [\<Assembly>](assembly-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución a todos los tipos de un ensamblado. Se trata de un elemento secundario de los elementos [\<Application>](application-element-net-native.md) y [\<Library>](library-element-net-native.md).  
  
 [\<AttributeImplies>](attributeimplies-element-net-native.md)  
 Si la directiva [\<Type>](type-element-net-native.md) que contiene es un atributo, aplica la directiva en tiempo de ejecución a los elementos de código a los que se les aplica dicho atributo.  
  
 [\<Directives>](directives-element-net-native.md)  
 Elemento raíz de cada archivo de directivas en tiempo de ejecución para .NET Native. Sus elementos secundarios son [\<Application>](application-element-net-native.md) y [\<Library>](library-element-net-native.md).  
  
 [\<Event>](event-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución a un evento. Se trata de un elemento secundario de los elementos [\<Type>](type-element-net-native.md) y [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<Field>](field-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución a un campo. Se trata de un elemento secundario de los elementos [\<Type>](type-element-net-native.md) y [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<GenericParameter>](genericparameter-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución al tipo de parámetro de un método o tipo genérico.  
  
 [\<ImpliesType>](impliestype-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución a un tipo, si dicha directiva se ha aplicado al tipo contenedor o al método.  
  
 [\<Library>](library-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución a todos los tipos de un ensamblado. Se trata de un elemento secundario de los elementos [\<Application>](application-element-net-native.md) y [\<Library>](library-element-net-native.md).  
  
 [\<Method>](method-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución a un método. Se trata de un elemento secundario de los elementos [\<Type>](type-element-net-native.md) y [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<MethodInstantiation>](methodinstantiation-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución a un método genérico construido. Se trata de un elemento secundario de los elementos [\<Type>](type-element-net-native.md) y [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<Namespace>](namespace-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución a todos los tipos de un espacio de nombres.  
  
 [\<Parameter>](parameter-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución al tipo del argumento que se pasa a un método.  
  
 [\<Property>](property-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución a una propiedad. Se trata de un elemento secundario de los elementos [\<Type>](type-element-net-native.md) y [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<Subtypes>](subtypes-element-net-native.md)  
 Aplica la directiva en tiempo de ejecución a todas las clases heredadas del tipo contenedor.  
  
 [\<Type>](type-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución a un tipo.  
  
 [\<TypeInstantiation>](typeinstantiation-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución a un tipo genérico construido.  
  
 [\<TypeParameter>](typeparameter-element-net-native.md)  
 Aplica la directiva de tiempo de ejecución al tipo representado por un argumento <xref:System.Type> que se pasa a un método.  
  
## <a name="see-also"></a>Vea también

- [Referencia del archivo de configuración rd.xml](runtime-directives-rd-xml-configuration-file-reference.md)
