---
title: x:FactoryMethod (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 586965dd4094e81fd830a09b64604cf33f195630
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053776"
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod (Directiva)
Especifica un método que no es un constructor que un procesador XAML debe utilizar para inicializar un objeto después de resolver su tipo de respaldo.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>Uso de atributos XAML, no x:Arguments  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>Uso de atributos XAML, x:Arguments como elemento (s)  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`methodname`|El nombre del método de cadena de un método que los procesadores XAML llaman para inicializar `object`la instancia especificada como. Vea la sección Comentarios.|  
|`oneOrMoreObjectElements`|Uno o más elementos de objeto para los objetos que especifican Factory Method parámetros. El orden es significativo; indica el orden en que los argumentos se deben pasar a la Factory Method.|  
  
## <a name="remarks"></a>Comentarios  
 Si `methodname` es un método de instancia, no se puede calificar.  
  
 Se admiten métodos estáticos como métodos de generador. Si `methodname` es un método estático, `methodname` se proporciona como un *TypeName*.la combinación MethodName, donde *TypeName* nombra la clase que define el Factory Method estático. *TypeName* se puede calificar como prefijo si se hace referencia a un tipo en un xmlns asignado. *TypeName* puede ser un tipo distinto de `typeof(object)`.  
  
 El Factory Method debe ser un método público declarado del tipo que respalda el elemento de objeto pertinente.  
  
 El Factory Method debe devolver una instancia de que se pueda asignar al objeto correspondiente. Los métodos de generador nunca deben devolver null.  
  
 `x:Arguments`funciona en un principio de la mejor coincidencia para las signaturas de los métodos de generador. La búsqueda de coincidencias evalúa primero el número de parámetros. Si hay más de una coincidencia posible para el recuento de parámetros, se evalúa el tipo de parámetro y se determina la mejor coincidencia. Si todavía hay ambigüedad después de esta fase de evaluación, el comportamiento del procesador XAML es indefinido.  
  
 El `x:FactoryMethod` uso del elemento no es el uso del elemento de propiedad en el sentido típico, porque el marcado de directivas no hace referencia al tipo del elemento de objeto contenedor. Se espera que el uso de elementos sea menos común que el uso de atributos. `x:Arguments`(el uso de atributo o elemento) se puede usar junto `x:FactoryMethod` con el uso de elementos, pero esto no se muestra específicamente en las secciones de uso.  
  
 `x:FactoryMethod`Dado que un elemento debe preceder a cualquier otro elemento de propiedad `x:Arguments` , debe preceder a cualquier elemento que se proporcione también como elemento y debe preceder a cualquier texto de contenido/texto interno/inicialización.  
  
## <a name="see-also"></a>Vea también

- [x:Arguments (directiva)](x-arguments-directive.md)
