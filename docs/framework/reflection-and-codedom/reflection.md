---
title: Reflexión en .NET
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET], reflection
- EventInfo class, reflection
- common language runtime, reflection
- FieldInfo class, reflection
- ParameterInfo class, reflection
- ConstructorInfo class, reflection
- Assembly class, reflection
- value types, reflection
- reflection, about reflection
- modules, reflection
- runtime, reflection
- Module class, reflection
- MethodInfo class, reflection
- PropertyInfo class, reflection
- type browsers
- reflection
- discovering type information at run time
- type system, reflection
ms.assetid: d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775
ms.openlocfilehash: 90d9cf4c473d73d1eeeb5f2a1098f8626c20359f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180472"
---
# <a name="reflection-in-net"></a>Reflexión en .NET

Las clases del espacio de nombres <xref:System.Reflection>, junto con <xref:System.Type?displayProperty=nameWithType>, permiten obtener información sobre los [ensamblados](../../standard/assembly/index.md) cargados y los tipos definidos dentro de ellos, como [clases](../../standard/base-types/common-type-system.md#classes), [interfaces](../../standard/base-types/common-type-system.md#interfaces) y tipos de valor (es decir, [estructuras](../../standard/base-types/common-type-system.md#structures) y [enumeraciones](../../standard/base-types/common-type-system.md#enumerations)). También puede usar la reflexión para crear instancias de tipos en tiempo de ejecución, para llamarlas y para acceder a ellas. Para consultar temas sobre aspectos específicos de la reflexión, vea los [Temas relacionados](#related_topics) al final de esta introducción.
  
El cargador de [Common Language Runtime](../../standard/clr.md) administra [dominios de aplicación](../app-domains/application-domains.md), que constituyen los límites definidos alrededor de los objetos que tienen el mismo ámbito de aplicación. Esta administración incluye la carga de cada ensamblado en el dominio de aplicación apropiado y el control del diseño de memoria de la jerarquía de tipos de cada ensamblado.  
  
Los [ensamblados](../app-domains/index.md) contienen módulos, los módulos contienen tipos y los tipos contienen miembros. La reflexión proporciona objetos que encapsulan ensamblados, módulos y tipos. Puede usar la reflexión para crear dinámicamente una instancia de un tipo, enlazar el tipo a un objeto existente u obtener el tipo desde un objeto existente. Después, puede invocar los métodos del tipo o acceder a sus campos y propiedades. Normalmente, la reflexión se usa para lo siguiente:  
  
- Use <xref:System.Reflection.Assembly> para definir y cargar ensamblados, cargar módulos enumerados en el manifiesto del ensamblado y buscar un tipo en este ensamblado y crear una instancia a partir de él.  
  
- Use <xref:System.Reflection.Module> para detectar información, como el ensamblado que contiene el módulo y las clases del módulo. También puede obtener todos los métodos globales u otros métodos específicos no globales definidos en el módulo.  
  
- Use <xref:System.Reflection.ConstructorInfo> para detectar información, como el nombre, los parámetros, los modificadores de acceso (por ejemplo, `public` o `private`) y detalles de implementación (por ejemplo, `abstract` o `virtual`) de un constructor. Use el método <xref:System.Type.GetConstructors%2A> o <xref:System.Type.GetConstructor%2A> de un <xref:System.Type> para invocar un constructor específico.  
  
- Use <xref:System.Reflection.MethodInfo> para detectar información, como el nombre, el tipo de retorno, los parámetros, los modificadores de acceso (por ejemplo, `public` o `private`) y detalles de implementación (por ejemplo, `abstract` o `virtual`) de un método. Use el método <xref:System.Type.GetMethods%2A> o <xref:System.Type.GetMethod%2A> de un <xref:System.Type> para invocar un método específico.  
  
- Use <xref:System.Reflection.FieldInfo> para detectar información como el nombre, los modificadores de acceso (por ejemplo, `public` o `private`) y detalles de la implementación (por ejemplo, `static`) de un campo, así como para obtener o establecer los valores del campo.  
  
- Use <xref:System.Reflection.EventInfo> para detectar información, como el nombre, el tipo de datos del controlador de eventos, los atributos personalizados, el tipo declarativo y el tipo reflejado de un evento, y para agregar o quitar controladores de eventos.  
  
- Use <xref:System.Reflection.PropertyInfo> para detectar información, como el nombre, el tipo de datos, la declaración de tipo, el tipo reflejado y el estado de solo lectura o de escritura de una propiedad, así como para obtener o establecer los valores de la propiedad.  
  
- Use <xref:System.Reflection.ParameterInfo> para detectar información, como el nombre del parámetro, el tipo de datos, si un parámetro es de entrada o de salida, y la posición del parámetro en una firma de método.  
  
- Use <xref:System.Reflection.CustomAttributeData> para detectar información sobre atributos personalizados cuando se trabaja en el contexto de solo reflexión de un dominio de aplicación. <xref:System.Reflection.CustomAttributeData> permite examinar los atributos sin crear instancias de ellos.  
  
Las clases del espacio de nombres <xref:System.Reflection.Emit> proporcionan una forma especializada de reflexión que permite compilar tipos en tiempo de ejecución.  
  
La reflexión también se puede usar para crear aplicaciones llamadas exploradores de tipos, que permiten a los usuarios seleccionar tipos y, después, ver la información sobre esos tipos.  
  
La reflexión tiene otros usos. Los compiladores de lenguajes como JScript usan la reflexión para generar tablas de símbolos. Las clases del espacio de nombres <xref:System.Runtime.Serialization> usan la reflexión para acceder a los datos y para determinar los campos que se deben conservar. Las clases del espacio de nombres <xref:System.Runtime.Remoting> usan la reflexión indirectamente a través de la serialización.  
  
## <a name="runtime-types-in-reflection"></a>Tipos de reflexión en tiempo de ejecución  
La reflexión proporciona clases, como <xref:System.Type> y <xref:System.Reflection.MethodInfo>, para representar tipos, miembros, parámetros y otras entidades de código. Pero cuando se usa la reflexión no se trabaja directamente con estas clases, porque la mayoría son abstractas (`MustInherit` en Visual Basic). En su lugar, se trabaja con tipos proporcionados por Common Language Runtime (CLR).  
  
Por ejemplo, cuando se usa el operador de C# `typeof` (`GetType` en Visual Basic) para obtener un objeto <xref:System.Type>, el objeto es en realidad un `RuntimeType`. `RuntimeType` deriva de <xref:System.Type> y proporciona implementaciones de todos los métodos abstractos.  
  
Estas clases en tiempo de ejecución son `internal` (`Friend` en Visual Basic). No se documentan por separado de sus clases base, ya que su comportamiento se describe en la documentación de la clase base.  
  
<a name="related_topics"></a>

## <a name="related-topics"></a>Temas relacionados  
  
|Title|Descripción|  
|-----------|-----------------|  
|[Ver información tipos](viewing-type-information.md)|Describe la clase <xref:System.Type> y proporciona ejemplos de código que muestran cómo usar <xref:System.Type> con diversas clases de reflexión para obtener información sobre constructores, métodos, campos, propiedades y eventos.|  
|[Reflexión y tipos genéricos](reflection-and-generic-types.md)|Explica cómo la reflexión controla los parámetros de tipo y los argumentos de tipo de tipos genéricos y métodos genéricos.|  
|[Consideraciones de seguridad sobre la reflexión](security-considerations-for-reflection.md)|Describe las reglas que determinan hasta qué punto se puede usar la reflexión para detectar la información sobre tipos y acceder a los tipos.|  
|[Cargar y usar tipos dinámicamente](dynamically-loading-and-using-types.md)|Describe la interfaz de enlace personalizado de reflexión que admite enlace de tiempo de ejecución.|  
|[Cómo: Cargar ensamblados en el contexto de solo reflexión](how-to-load-assemblies-into-the-reflection-only-context.md)|Describe el contexto de carga de solo reflexión. Muestra cómo cargar un ensamblado, cómo probar el contexto y cómo examinar los atributos aplicados a un ensamblado en el contexto de solo reflexión.|  
|[Acceso a atributos personalizados](accessing-custom-attributes.md)|Muestra cómo usar la reflexión para consultar la existencia de atributos y sus valores.|  
|[Especificar nombres de tipo completos](specifying-fully-qualified-type-names.md)|Describe el formato de nombres de tipo completos en términos del formulario Backus-Naur (BNF) así como la sintaxis necesaria para especificar caracteres especiales, nombres de ensamblados, punteros, referencias y matrices.|  
|[Cómo: Enlazar un delegado mediante la reflexión](how-to-hook-up-a-delegate-using-reflection.md)|Explica cómo crear un delegado para un método y enlazar el delegado a un evento. Explica cómo crear un método de control de eventos en tiempo de ejecución mediante <xref:System.Reflection.Emit.DynamicMethod>.|  
|[Emitir métodos y ensamblados dinámicos](emitting-dynamic-methods-and-assemblies.md)|Explica cómo generar ensamblados y métodos dinámicos.|  
  
## <a name="reference"></a>Referencia  

<xref:System.Type?displayProperty=nameWithType>  
  
<xref:System.Reflection>  
  
<xref:System.Reflection.Emit>  
