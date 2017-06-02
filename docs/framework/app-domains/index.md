---
title: "Programar con dominios de aplicación y ensamblados | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1cfd73bf6d8de9ea4ff9854e6882683514cb3c56
ms.contentlocale: es-es
ms.lasthandoff: 06/02/2017

---
# <a name="programming-with-application-domains-and-assemblies"></a>Programar con dominios de aplicación y ensamblados
Hosts como Microsoft Internet Explorer, ASP.NET y el shell de Windows cargan Common Language Runtime en un proceso, crean un [dominio de aplicación](../../../docs/framework/app-domains/application-domains.md) en ese proceso y luego cargan y ejecutan el código de usuario en ese dominio de aplicación cuando se ejecuta una aplicación de .NET Framework. En la mayoría de los casos, no tiene que preocuparse por crear dominios de aplicación y cargar ensamblados en ellos porque el host en tiempo de ejecución realiza esas tareas.  
  
 Sin embargo, si crea una aplicación que hospedará Common Language Runtime, crea herramientas o código que desea descargar mediante programación o crea componentes acoplables que se pueden descargar y cargar sobre la marcha, creará sus propios dominios de aplicación. Incluso si no crea un host en tiempo de ejecución, esta sección proporciona información importante sobre cómo trabajar con dominios de aplicación y los ensamblados cargados en estos.  
  
## <a name="in-this-section"></a>En esta sección  
 [Temas "Cómo..." sobre dominios de aplicación y ensamblados](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 Proporciona vínculos a todos los temas de procedimientos que se encuentran en la documentación conceptual para programación con dominios de aplicación y ensamblados.  
  
 [Utilizar dominios de aplicación](../../../docs/framework/app-domains/use.md)  
 Proporciona ejemplos sobre cómo crear, configurar y usar dominios de aplicación.  
  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Describe cómo crear, firmar y establecer atributos en los ensamblados.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Emitir métodos y ensamblados dinámicos](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 Describe la creación de ensamblados dinámicos.  
  
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Proporciona una introducción general a los conceptos de los ensamblados.  
  
 [Dominios de aplicación](../../../docs/framework/app-domains/application-domains.md)  
 Proporciona una introducción general a los conceptos de los dominios de aplicación.  
  
 [Información general de la reflexión](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.
