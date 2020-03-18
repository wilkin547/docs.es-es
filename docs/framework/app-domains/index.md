---
title: Programar con dominios de aplicación y ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
ms.openlocfilehash: 2c849d27c70971d17bf4359ee7ae1081ee976a5f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73119818"
---
# <a name="programming-with-application-domains-and-assemblies"></a>Programar con dominios de aplicación y ensamblados

Hosts como Microsoft Internet Explorer, ASP.NET y el shell de Windows cargan Common Language Runtime en un proceso, crean un [dominio de aplicación](application-domains.md) en ese proceso y luego cargan y ejecutan el código de usuario en ese dominio de aplicación cuando se ejecuta una aplicación de .NET Framework. En la mayoría de los casos, no tiene que preocuparse por crear dominios de aplicación y cargar ensamblados en ellos porque el host en tiempo de ejecución realiza esas tareas.  
  
Sin embargo, si crea una aplicación que hospedará Common Language Runtime, crea herramientas o código que desea descargar mediante programación o crea componentes acoplables que se pueden descargar y cargar sobre la marcha, creará sus propios dominios de aplicación. Incluso si no crea un host en tiempo de ejecución, esta sección proporciona información importante sobre cómo trabajar con dominios de aplicación y los ensamblados cargados en estos.  
  
## <a name="in-this-section"></a>En esta sección  

[Temas "Cómo..." sobre dominios de aplicación y ensamblados](application-domains-and-assemblies-how-to-topics.md)  
Proporciona vínculos a todos los temas de procedimientos que se encuentran en la documentación conceptual para programación con dominios de aplicación y ensamblados.  
  
[Utilizar dominios de aplicación](use.md)  
Proporciona ejemplos sobre cómo crear, configurar y usar dominios de aplicación.  
  
[Programar con ensamblados](../../standard/assembly/program.md)  
Describe cómo crear, firmar y establecer atributos en los ensamblados.  
  
## <a name="related-sections"></a>Secciones relacionadas  

[Emitir métodos y ensamblados dinámicos](../reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
Describe la creación de ensamblados dinámicos.  
  
[Ensamblados de .NET](../../standard/assembly/index.md)  
Proporciona una introducción general a los conceptos de los ensamblados.  
  
[Dominios de aplicación](application-domains.md)  
Proporciona una introducción general a los conceptos de los dominios de aplicación.  
  
[Información general de la reflexión](../reflection-and-codedom/reflection.md)  
Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.
