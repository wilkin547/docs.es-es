---
title: Portabilidad a .NET Core desde .NET Framework
description: "Comprenda el proceso de portabilidad y descubra herramientas que le pueden resultar útiles al realizar la portabilidad de un proyecto de .NET Framework a .NET Core."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 00d00d38-99af-44f4-a75f-defcd9729dc5
ms.translationtype: HT
ms.sourcegitcommit: 3155295489e1188640dae5aa5bf9fdceb7480ed6
ms.openlocfilehash: 4fc68a3dbdec634d8e92a066a46939ba19c65db7
ms.contentlocale: es-es
ms.lasthandoff: 08/05/2017

---

# <a name="porting-to-net-core-from-net-framework"></a>Portabilidad a .NET Core desde .NET Framework

Si tiene código que se ejecuta en .NET Framework, puede que le interese ejecutarlo en .NET Core 1.0.  Este artículo es una introducción al proceso de portabilidad y describe una lista de las herramientas que puede encontrar de utilidad al realizar la portabilidad a .NET Core.

## <a name="overview-of-the-porting-process"></a>Información general sobre el proceso de portabilidad

El proceso recomendado para realizar la portabilidad sigue estos pasos.  Cada una de estas partes del proceso se trata con más detalle en otros artículos.

1. Identifique y tenga en cuenta las dependencias de terceros.

   Esto implica comprender lo que son las dependencias de terceros, cómo depende de ellas, cómo ver si también se ejecutan en .NET Core y los pasos que puede seguir si no lo hacen.
   
2. Redirigir todos los proyectos que desee portar a .NET Framework 4.6.2 de destino.

   Esto garantiza que puede usar alternativas de API para destinos específicos de .NET Framework en los casos donde .NET Core no pueda admitir una API determinada.
   
3. Use la [herramienta API Portability Analyzer](https://github.com/Microsoft/dotnet-apiport/) para analizar los ensamblados y desarrollar un plan para realizar la portabilidad basándose en los resultados.

   Esta herramienta analiza los ensamblados compilados y genera un informe que muestra un resumen de portabilidad de alto nivel, junto con un desglose de cada API que usa que no está disponible en .NET Core.  Puede usar este informe junto con un análisis de su código base para desarrollar un plan de cómo portar el código.
   
4. Porte el código de prueba.

   Dado que portar a .NET Core es un cambio tan grande para el código base, se recomienda encarecidamente portar las pruebas de forma que pueda ejecutarlas mientras porta el código.  MSTest, xUnit y NUnit todos admiten actualmente .NET Core 1.0.
   
6. Ejecute el plan de portabilidad.

## <a name="tools-to-help"></a>Herramientas de ayuda

Esta es una pequeña lista de las herramientas que puede encontrar de utilidad:

* NuGet: [Nuget Client](https://dist.nuget.org/index.html) o [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), el administrador de paquetes de Microsoft para implementaciones de .NET.
* Api Portability Analyzer: [herramienta de línea de comandos](https://github.com/Microsoft/dotnet-apiport/releases) o [Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b), una cadena de herramientas que puede generar un informe de lo portátil que es su código entre .NET Framework y .NET Core, con un desglose de problemas ensamblado por ensamblado.  Para más información, consulte las [herramientas para ayudarle en el proceso](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).
* Reverse Package Search: un [servicio web útil](https://packagesearch.azurewebsites.net) que le permite buscar un tipo y encontrar los paquetes que lo contienen.

## <a name="next-steps"></a>Pasos siguientes

[Análisis de las dependencias de terceros.](third-party-deps.md)
   

