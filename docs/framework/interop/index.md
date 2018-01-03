---
title: "Interoperar con código no administrado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f475877bcb7a794d1a58ef9202735e016363678b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="interoperating-with-unmanaged-code"></a>Interoperar con código no administrado
.NET Framework promueve la interacción con componentes COM, servicios COM+, bibliotecas de tipos externas y muchos servicios del sistema operativo. Los tipos de datos, las firmas de método y los mecanismos de control de errores varían entre los modelos de objetos administrados y no administrados. Para simplificar la interoperación entre los componentes de .NET Framework y el código no administrado, así como para facilitar la ruta de migración, Common Language Runtime oculta a los clientes y servidores las diferencias en estos modelos de objetos.  
  
 El código que se ejecuta bajo el control del tiempo de ejecución se denomina código administrado. Por el contrario, el código que se ejecuta fuera del tiempo de ejecución se denomina código no administrado. Los componentes COM, las interfaces ActiveX y las funciones de la API de Win32 son ejemplos de código no administrado.  
  
## <a name="in-this-section"></a>En esta sección  
 [Temas sobre cómo interoperar con código no administrado](http://msdn.microsoft.com/en-us/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 Proporciona vínculos a todos los temas de procedimientos que se encuentran en la documentación conceptual para interoperar con código no administrado.  
  
 [Exponer componentes COM en .NET Framework](../../../docs/framework/interop/exposing-com-components.md)  
 Se describe cómo usar los componentes COM desde las aplicaciones de .NET Framework.  
  
 [Exponer componentes de .NET Framework en COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Se describe cómo usar los componentes de .NET Framework desde las aplicaciones COM.  
  
 [Consumir funciones DLL no administradas](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 Se describe cómo llamar a funciones DLL no administradas mediante la invocación de plataforma.  
  
 [Consideraciones de diseño para interoperaciones](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 Proporciona sugerencias para escribir componentes COM integrados.  
  
 [Serialización de interoperabilidad](../../../docs/framework/interop/interop-marshaling.md)  
 Se describe la serialización de la interoperabilidad COM y la invocación de plataforma.  
  
 [Asignar resultados HRESULT y excepciones](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 Se describe la asignación entre las excepciones y los valores HRESULT.  
  
 [Interoperar utilizando tipos genéricos](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 Se describe el comportamiento de los tipos genéricos cuando se usan en la interoperabilidad COM.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Interoperabilidad COM avanzada](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Proporciona vínculos a más información sobre la incorporación de componentes COM en una aplicación de .NET Framework.
