---
title: "Exposing .NET Framework Components to COM | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "exposing .NET Framework components to COM"
  - "interoperation with unmanaged code, exposing .NET Framework components"
  - "COM interop, exposing COM components"
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Exposing .NET Framework Components to COM
Escribir un tipo .NET y consumirlo desde el código no administrado son actividades distintas para los programadores.  En esta sección se describen varias sugerencias para escribir código administrado que interopera con clientes COM:  
  
-   [Calificar tipos de .NET para la interoperación](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).  
  
     Todos los tipos, métodos, propiedades, campos y eventos administrados que desee exponer a COM deben ser públicos.  Los tipos deben tener un constructor predeterminado público, que es el único al que se puede llamar mediante COM.  
  
-   [Aplicar atributos de interoperabilidad](../../../docs/framework/interop/applying-interop-attributes.md).  
  
     Los atributos personalizados del código administrado pueden mejorar la interoperabilidad de un componente.  
  
-   [Empaquetar un ensamblado para COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md).  
  
     Es posible que los programadores de COM necesiten que el usuario resuma los pasos llevados a cabo para hacer referencias e implementar ensamblados.  
  
 Además, en esta sección se identifican las tareas relacionadas con el consumo de un tipo administrado desde un cliente COM.  
  
#### Para consumir un tipo administrado desde COM  
  
1.  [Registre ensamblados con COM](../../../docs/framework/interop/registering-assemblies-with-com.md).  
  
     Los tipos de un ensamblado \(y bibliotecas de tipos\) deben registrarse en tiempo de diseño.  Si un instalador no registra el ensamblado, pida a los programadores de COM que utilicen Regasm.exe.  
  
2.  [Haga referencia a tipos de .NET desde COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md).  
  
     Los programadores de COM pueden hacer referencia a los tipos de un ensamblado con las mismas herramientas y técnicas que utilizan en la actualidad.  
  
3.  [Llame a un objeto de .NET](http://msdn.microsoft.com/es-es/40c9626c-aea6-4bad-b8f0-c1de462efd33).  
  
     Los programadores de COM pueden llamar a métodos en el objeto .NET de la misma manera que lo hacen en cualquier tipo no administrado.  Por ejemplo, la API **CoCreateInstance** de COM activa objetos .NET.  
  
4.  [Implemente una aplicación para obtener acceso a COM](http://msdn.microsoft.com/es-es/fb63564c-c1b9-4655-a094-a235625882ce).  
  
     Un ensamblado con nombre seguro puede instalarse en una caché global de ensamblados y requiere una firma de su editor.  Los ensamblados que no tienen nombre seguro deben instalarse en el directorio de la aplicación del cliente.  
  
## Vea también  
 [Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md)   
 [COM Interop Sample: COM Client and .NET Server](../../../docs/framework/interop/com-interop-sample-com-client-and-net-server.md)