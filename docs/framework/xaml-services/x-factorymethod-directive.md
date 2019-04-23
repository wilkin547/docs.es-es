---
title: x:FactoryMethod (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 8fff4d62e07bdfd4ecc27d2692c391251afdd6d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190696"
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod (Directiva)
Especifica un método distinto de un constructor que un procesador XAML debe usar para inicializar un objeto después de resolver su tipo de respaldo.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>Uso de atributos XAML, no hay x: Arguments  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>Uso de atributos XAML, x: Arguments como elementos  
  
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
|`oneOrMoreObjectElements`|Uno o más elementos de objeto para objetos que especifican los parámetros de método de fábrica. El orden es importante; significa el orden en el que se deben pasar argumentos al método de generador.|  
  
## <a name="remarks"></a>Comentarios  
 Si `methodname` es un método de instancia, no se puede calificar.  
  
 Se admiten métodos estáticos como métodos de generador. Si `methodname` es un método estático, `methodname` se proporciona como un *typeName*. *methodName* combinación, donde *typeName* nombra la clase que define el método de generador estático. *typeName* puede estar calificado con un prefijo si hace referencia a un tipo en un atributo xmlns asignado. *typeName* puede ser un tipo diferente al `typeof(object)`.  
  
 El método de generador debe ser un método declarado público del tipo que respalda el elemento del objeto pertinente.  
  
 El método de generador debe devolver una instancia que se puede asignar al objeto pertinente. Métodos de generador nunca deben devolver nulos.  
  
 `x:Arguments` opera en un principio de la mejor coincidencia para las firmas de métodos de generador. Coincidencia, el número de parámetros evalúa primero. Si hay más de una coincidencia posible para un número de parámetros, tipo de parámetro es, a continuación, evalúa y la mejor coincidencia vendrá determinada. Si todavía hay ambigüedad después de esta fase de evaluación, el comportamiento del procesador XAML es indefinido.  
  
 El `x:FactoryMethod` uso del elemento no es el uso de elementos de propiedad en el sentido típico, porque el marcado de la directiva no hace referencia el tipo del elemento de objeto que contiene. Se espera que el uso de elemento es menos común que el uso de atributos. `x:Arguments` (uso del atributo o elemento) que puede usarse junto con `x:FactoryMethod` uso de elementos, pero esto no se muestren específicamente en las secciones de uso.  
  
 `x:FactoryMethod` como un elemento debe preceder a cualquier otro elemento de propiedad, debe preceder a cualquier `x:Arguments` también proporcionados como elementos y deben preceder a cualquier texto de inicialización de texto o contenido interno.  
  
## <a name="see-also"></a>Vea también

- [x:Arguments (directiva)](x-arguments-directive.md)
