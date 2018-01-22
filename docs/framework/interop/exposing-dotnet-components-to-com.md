---
title: Exponer componentes de .NET Framework en COM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a3d34c60a5c2cae5abaa6763b935f6d11a29a39e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="exposing-net-framework-components-to-com"></a>Exponer componentes de .NET Framework en COM
Escribir un tipo .NET y consumirlo desde código no administrado son actividades distintas para los desarrolladores. En esta sección se describen varias sugerencias para escribir código administrado que interopere con clientes COM:  
  
-   [Habilitar tipos de .NET para la interoperación](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).  
  
     Todos los tipos, métodos, propiedades, campos y eventos administrados que desee exponer a COM deben ser públicos. Los tipos deben tener un constructor predeterminado público, que es el único al que se puede llamar mediante COM.  
  
-   [Aplicar atributos de interoperabilidad](../../../docs/framework/interop/applying-interop-attributes.md).  
  
     Los atributos personalizados de código administrado pueden mejorar la interoperabilidad de un componente.  
  
-   [Empaquetar un ensamblado para COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md).  
  
     Es posible que los programadores de COM requieran que resuma los pasos necesarios para hacer referencia a los ensamblados e implementarlos.  
  
 Además, en esta sección se identifican las tareas relacionadas con el consumo de un tipo administrado desde un cliente COM.  
  
#### <a name="to-consume-a-managed-type-from-com"></a>Para consumir un tipo administrado desde COM  
  
1.  [Registrar ensamblados con COM](../../../docs/framework/interop/registering-assemblies-with-com.md).  
  
     Los tipos de un ensamblado (y bibliotecas de tipos) deben registrarse en tiempo de diseño. Si un instalador no registra el ensamblado, indique a los programadores de COM que usen Regasm.exe.  
  
2.  [Hacer referencia a tipos de .NET desde COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md).  
  
     Los desarrolladores de COM pueden hacer referencia a tipos en un ensamblado con las mismas herramientas y técnicas que usan actualmente.  
  
3.  [Llamar a un objeto de .NET](http://msdn.microsoft.com/library/40c9626c-aea6-4bad-b8f0-c1de462efd33).  
  
     Los desarrolladores de COM pueden llamar a métodos en el objeto .NET de la misma manera que llaman a los métodos de cualquier tipo no administrado. Por ejemplo, la API **CoCreateInstance** de COM activa objetos .NET.  
  
4.  [Implementar una aplicación para obtener acceso a COM](http://msdn.microsoft.com/library/fb63564c-c1b9-4655-a094-a235625882ce).  
  
     Un ensamblado con nombre seguro puede instalarse en la caché global de ensamblados y requiere una firma de su editor. Los ensamblados que no tienen nombre seguro deben instalarse en el directorio de aplicación del cliente.  
  
## <a name="see-also"></a>Vea también  
 [Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md) (Interoperar con código no administrado)  
 [Ejemplo de interoperabilidad COM: cliente COM y servidor .NET](../../../docs/framework/interop/com-interop-sample-com-client-and-net-server.md)
