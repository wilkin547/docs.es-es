---
title: "Interoperating with Unmanaged Code | Microsoft Docs"
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
  - "unmanaged code, interoperation"
  - "managed code, interoperation with unmanaged code"
  - ".NET Framework, interoperation with unmanaged code"
  - "unmanaged code"
  - "interoperation with unmanaged code"
  - "interoperation with unmanaged code, about interoperation"
  - "components [.NET Framework], interoperation with unmanaged code"
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Interoperating with Unmanaged Code
.NET Framework promueve la interacción con los componentes COM, los Servicios COM\+, las bibliotecas de tipos externas y muchos servicios del sistema operativo.  Los tipos de datos, los prototipos de los métodos y los mecanismos de control de errores no son iguales en los modelos de objetos administrados y no administrados.  Para simplificar la interoperación entre los componentes de .NET Framework y el código no administrado y facilitar la ruta de acceso de migración, Common Language Runtime oculta las diferencias que existen entre estos modelos de objetos a los clientes y a los servidores.  
  
 El código que se ejecuta bajo el control del motor en tiempo de ejecución se denomina código administrado.  Por el contrario, el código que se ejecuta fuera del motor en tiempo de ejecución se denomina código no administrado.  Los componentes COM, las interfaces ActiveX y las funciones de la API Win32 son ejemplos de código no administrado.  
  
## En esta sección  
 [Interoperating with Unmanaged Code How\-to Topics](http://msdn.microsoft.com/es-es/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 Contiene vínculos a todos los temas "Cómo..." incluidos en la documentación conceptual para la interoperabilidad con código no administrado.  
  
 [Exponer componentes COM en .NET Framework](../../../docs/framework/interop/exposing-com-components.md)  
 Describe cómo se utilizan los componentes COM en las aplicaciones de .NET Framework.  
  
 [Exponer componentes de .NET Framework en COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Describe cómo se utilizan los componentes de .NET Framework en las aplicaciones COM.  
  
 [Consumir funciones DLL no administradas](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 Describe cómo llamar a funciones no administradas de archivos DLL mediante invocación de plataforma.  
  
 [Consideraciones de diseño para interoperaciones](http://msdn.microsoft.com/es-es/b59637f6-fe35-40d6-ae72-901e7a707689)  
 Se proporcionan sugerencias para escribir componentes COM integrados.  
  
 [Cálculo de referencias de interoperabilidad](../../../docs/framework/interop/interop-marshaling.md)  
 Describe el cálculo de referencias de datos para la interoperabilidad COM y la invocación de plataformas.  
  
 [How to: Map HRESULTs and Exceptions](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 Describe la asignación entre excepciones y resultados HRESULT.  
  
 [Interoperating Using Generic Types](http://msdn.microsoft.com/es-es/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 Describe el comportamiento de tipos genéricos cuando se utiliza en interoperabilidad COM.  
  
## Secciones relacionadas  
 [Advanced COM Interoperability](http://msdn.microsoft.com/es-es/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Proporciona vínculos a más información sobre cómo incorporar los componentes COM a su aplicación .NET Framework.