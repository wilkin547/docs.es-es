---
title: x:FactoryMethod (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 5e864b6f5d664b079036a5d915e2f6f81b83639f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432789"
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod (Directiva)
Especifica un método distinto de un constructor que un procesador XAML debe usar para inicializar un objeto después de resolver su tipo de respaldo.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>Uso de atributos XAML, sin x:Arguments  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>Uso de atributos XAML, x:Arguments as Element(s)  
  
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
|`methodname`|El nombre del método de cadena de un método `object`al que llaman los procesadores XAML para inicializar la instancia especificada como . Vea la sección Comentarios.|  
|`oneOrMoreObjectElements`|Uno o varios elementos de objeto para objetos que especifican parámetros de método de fábrica. El orden es significativo; significa el orden en que los argumentos deben pasarse al método de fábrica.|  
  
## <a name="remarks"></a>Observaciones  
 Si `methodname` es un método de instancia, no se puede calificar.  
  
 Se admiten métodos estáticos como métodos de fábrica. Si `methodname` es un `methodname` método estático, `typeName.methodName` se `typeName` proporciona como una combinación, donde nombra la clase que define el método de fábrica estático. `typeName`puede ser calificado por prefijo si se hace referencia a un tipo en un xmlns asignado. `typeName`puede ser un `typeof(object)`tipo diferente que .  
  
 El método factory debe ser un método público declarado del tipo que respalda el elemento de objeto relevante.  
  
 El método factory debe devolver una instancia que se pueda asignar al objeto relevante. Los métodos de fábrica nunca deben devolver null.  
  
 `x:Arguments`opera sobre un principio de mejor coincidencia para las firmas de los métodos de fábrica. La coincidencia evalúa primero el recuento de parámetros. Si hay más de una coincidencia posible para un recuento de parámetros, se evalúa el tipo de parámetro y se determina la mejor coincidencia. Si todavía hay ambiguedad después de esta fase de evaluación, el comportamiento del procesador XAML es indefinido.  
  
 El `x:FactoryMethod` uso del elemento no es el uso del elemento de propiedad en el sentido típico, porque el marcado de directiva no hace referencia al tipo del elemento de objeto contenedor. Se espera que el uso de elementos sea menos común que el uso de atributos. `x:Arguments`(uso de atributos o elementos) se puede utilizar junto con `x:FactoryMethod` el uso de elementos, pero esto no se muestra específicamente en las secciones Uso.  
  
 `x:FactoryMethod`como un elemento debe preceder a cualquier `x:Arguments` otro elemento de propiedad, debe preceder a cualquier elemento proporcionado también como y debe preceder a cualquier contenido/texto interno/texto de inicialización.  
  
## <a name="see-also"></a>Consulte también

- [x:Arguments (Directiva)](xarguments-directive.md)
