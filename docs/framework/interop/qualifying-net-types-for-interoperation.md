---
title: "Habilitar tipos de .NET para la interoperación"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, qualifying .NET types
- qualifying .NET types for interoperation
- interoperation with unmanaged code, qualifying .NET types
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b0a6d6a2a8139127b46484f972eb797642b4ee53
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="qualifying-net-types-for-interoperation"></a>Habilitar tipos de .NET para la interoperación
Si tiene previsto exponer tipos en un ensamblado a las aplicaciones COM, tenga en cuenta los requisitos de interoperabilidad COM en tiempo de diseño. Los tipos administrados (clase, interfaz, estructura y enumeración) se integran fácilmente con los tipos COM si se cumplen las directrices siguientes:  
  
-   Las clases deben implementar interfaces de forma explícita.  
  
     Aunque la interoperabilidad COM proporciona un mecanismo para generar automáticamente una interfaz que contiene todos los miembros de la clase y los miembros de su clase base, es mucho mejor proporcionar interfaces explícitas. La interfaz generada automáticamente se denomina interfaz de clase. Para obtener instrucciones detalladas, consulte [Introducción a la interfaz de clase](com-callable-wrapper.md#introducing-the-class-interface).  
  
     Puede utilizar Visual Basic, C# y C++ para incorporar las definiciones de interfaz en el código, en lugar de tener que utilizar el lenguaje de definición de interfaz (IDL) o su equivalente. Para obtener información detallada de la sintaxis, vea la documentación del lenguaje.  
  
-   Los tipos administrados deben ser públicos.  
  
     Solo los tipos públicos de un ensamblado se registran y se exportan a la biblioteca de tipos. Como resultado, solo los tipos públicos son visibles para COM.  
  
     Los tipos administrados exponen características a otro código administrado que es posible que no se expongan a COM. Por ejemplo, los constructores con parámetros, los métodos estáticos y los campos de constante no se exponen a los clientes COM. Además, como el tiempo de ejecución serializa los datos dentro y fuera de un tipo, es posible que los datos se copien o se transformen.  
  
-   Los métodos, las propiedades, los campos y los eventos deben ser públicos.  
  
     Los miembros de tipos públicos también deben ser públicos si van a ser visibles para COM. La aplicación de <xref:System.Runtime.InteropServices.ComVisibleAttribute> permite restringir la visibilidad de un ensamblado, un tipo público o miembros públicos de un tipo público. De forma predeterminada, todos los tipos y miembros públicos son visibles.  
  
-   Los tipos deben tener un constructor público predeterminado para que se activen desde COM.  
  
     Los tipos públicos administrados son visibles para COM. Pero sin un constructor público predeterminado (un constructor sin argumentos), los clientes COM no pueden crear el tipo. Los clientes COM todavía pueden usar el tipo si se activa por otros medios.  
  
-   Los tipos no pueden ser abstractos.  
  
     Ni los clientes COM ni los clientes .NET pueden crear tipos abstractos.  
  
 Cuando se exporta a COM, se simplifica la jerarquía de herencia de un tipo administrado. El control de versiones también difiere entre los entornos administrados y no administrados. Los tipos expuestos a COM no tienen las mismas características de control de versiones que otros tipos administrados.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>  
 [Exponer componentes de .NET Framework en COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [Introducción a la interfaz de clase](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024)  
 [Aplicar atributos de interoperabilidad](../../../docs/framework/interop/applying-interop-attributes.md)  
 [Empaquetar un ensamblado para COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md)
