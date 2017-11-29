---
title: x:FactoryMethod (Directiva)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 0d53db49961c2a75e4547f6b57240cefd2cc17c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod (Directiva)
Especifica un método que no sea un constructor que un procesador XAML debe usar para inicializar un objeto después de resolver su tipo de respaldo.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>Uso de atributos XAML, sin x: Arguments  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>Uso de atributos XAML, x: Arguments como elemento (s)  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`methodname`|El nombre del método de cadena de un método que llamen procesadores XAML para inicializar la instancia especificada como `object`. Vea la sección Comentarios.|  
|`oneOrMoreObjectElements`|Uno o más elementos de objeto para los objetos que especifican los parámetros de método de fábrica. El orden es importante; indica el orden en que los argumentos se deberían pasar al método de generador.|  
  
## <a name="remarks"></a>Comentarios  
 Si `methodname` es un método de instancia, no se puede calificar.  
  
 Se admiten métodos estáticos como métodos de generador. Si `methodname` es un método estático, `methodname` se proporciona como un *typeName*. *methodName* combinación, donde *typeName* nombre a la clase que define el método de generador estático. *typeName* puede ser calificada con prefijo si se hace referencia a un tipo en un xmlns asignado. *typeName* puede ser un tipo diferente de `typeof(``object``)`.  
  
 El método de generador debe ser un método público declarado del tipo que respalda el elemento de objeto pertinente.  
  
 El método de generador debe devolver una instancia que se puede asignar al objeto pertinente. Métodos de generador nunca deberían devolver nulos.  
  
 `x:Arguments`opera en un principio de mejor coincidencia para las firmas de métodos de generador. Búsqueda de coincidencias, el número de parámetros evalúa primero. Si hay más de una coincidencia posible para un recuento de parámetros, tipo de parámetro es, a continuación, evalúa y mejor coincidencia vendrá determinada. Si todavía no hay ambigüedad después de esta fase de evaluación, el comportamiento del procesador XAML es indefinido.  
  
 El `x:FactoryMethod` uso de elementos no es el uso de elementos de propiedad en el sentido típico, porque el marcado de la directiva no hace referencia el tipo del elemento de objeto contenedor. Se espera que el uso de elemento es menos común que el uso de atributos. `x:Arguments`(uso de atributo o elemento) que puede utilizarse junto con `x:FactoryMethod` uso de elementos, pero esto no se muestra específicamente en las secciones de uso.  
  
 `x:FactoryMethod`como un elemento debe preceder a cualquier otro elemento de propiedad, debe preceder a cualquier `x:Arguments` también proporcionado como elemento y debe preceder a cualquier texto de inicialización de texto de contenido o interna.  
  
## <a name="see-also"></a>Vea también  
 [x:Arguments (directiva)](../../../docs/framework/xaml-services/x-arguments-directive.md)
