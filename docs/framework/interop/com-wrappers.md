---
title: "COM Wrappers | Microsoft Docs"
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
  - "wrapper classes"
  - "COM interop, COM wrappers"
  - "COM wrappers"
  - "COM, wrappers"
  - "interoperation with unmanaged code, COM wrappers"
  - "COM callable wrappers"
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# COM Wrappers
COM se diferencia del modelo de objetos de .NET Framework en varios aspectos importantes:  
  
-   Los clientes de objetos COM deben administrar esos objetos mientras existan; Common Language Runtime administra la duración de objetos en su entorno.  
  
-   Los clientes de objetos COM detectan si un servicio está disponible solicitando una interfaz que proporciona ese servicio y obteniendo o no un puntero de interfaz.  Los clientes de objetos .NET pueden obtener una descripción de la funcionalidad de un objeto mediante la reflexión.  
  
-   Los objetos .NET residen en memoria administrada por el entorno de ejecución .NET Framework.  El entorno de ejecución puede mover los objetos de la memoria por razones de rendimiento y actualizar todas las referencias a los objetos que mueve.  Los clientes no administrados, una vez que han obtenido un puntero a un objeto, dependen del objeto para permanecer en la misma ubicación.  Estos clientes no tienen ningún mecanismo para tratar con objetos que no tengan una ubicación fija.  
  
 Para superar estas diferencias, el motor en tiempo de ejecución proporciona clases contenedoras para que tanto los clientes administrados como los no administrados crean que están llamando a objetos de su respectivo entorno.  Cuando un cliente administrado llama a un método en un objeto COM, el motor en tiempo de ejecución crea un [contenedor invocable en tiempo de ejecución](../../../docs/framework/interop/runtime-callable-wrapper.md) \(RCW\).  Entre otras cosas, los RCW analizan las diferencias entre los mecanismos de referencia administrados y no administrados.  El motor en tiempo de ejecución crea también un [contenedor CCW](../../../docs/framework/interop/com-callable-wrapper.md) \(COM callable wrapper\) para invertir el proceso, de modo que un cliente COM pueda llamar sin problemas a un método en un objeto .NET.  Como se muestra en la siguiente ilustración, la perspectiva del código de llamada determina la clase contenedora que crea el motor en tiempo de ejecución.  
  
 ![Información general sobre los contenedores COM](../../../docs/framework/interop/media/bidirectional.gif "bidirectional")  
Información general sobre los contenedores COM  
  
 En la mayoría de los casos, los RCW o CCW estándar que genera el motor en tiempo de ejecución proporcionan un cálculo de referencias adecuado para las llamadas que traspasan los límites entre COM y .NET Framework.  Mediante la utilización de atributos personalizados se puede ajustar, si se desea, la forma en que el motor en tiempo de ejecución representa los códigos administrado y no administrado.  
  
## Vea también  
 [Advanced COM Interoperability](http://msdn.microsoft.com/es-es/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md)   
 [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md)   
 [Customizing Standard Wrappers](http://msdn.microsoft.com/es-es/c40d089b-6a3c-41b5-a20d-d760c215e49d)   
 [How to: Customize Runtime Callable Wrappers](http://msdn.microsoft.com/es-es/4a4bb3da-4d60-4517-99f2-78d46a681732)