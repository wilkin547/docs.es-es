---
title: Portabilidad del código de .NET Framework a .NET Core
description: Comprenda el proceso de portabilidad y descubra herramientas que le pueden resultar útiles al realizar la portabilidad de un proyecto de .NET Framework a .NET Core.
author: cartermp
ms.author: mairaw
ms.date: 12/04/2018
ms.custom: seodec18
ms.openlocfilehash: 3ea6456d066261f521a793d34dcb73c129016280
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145155"
---
# <a name="port-your-code-from-net-framework-to-net-core"></a>Realice la portabilidad de su código de .NET Framework a .NET Core.

Si tiene código que se ejecuta en .NET Framework, puede que le interese ejecutarlo también en .NET Core. Esta es una introducción al proceso de portabilidad y una lista de las herramientas que puede encontrar de utilidad al portar el código a .NET Core.

## <a name="overview-of-the-porting-process"></a>Introducción al proceso de portabilidad

Este es el proceso que se recomienda al portar un proyecto a .NET Core. Cada paso del proceso se trata con más detalle en otros artículos.

1. Identifique y tenga en cuenta las dependencias de terceros.

   Este paso implica comprender lo que son las dependencias de terceros, cómo depende de ellas, cómo comprobar si también se ejecutan en .NET Core y los pasos que puede seguir si no lo hacen. También se describe cómo migrar las dependencias al formato [PackageReference](/nuget/consume-packages/package-references-in-project-files) que se usa en .NET Core.

2. Redirija todos los proyectos que desee portar a .NET Framework 4.7.2 o superior.

   Este paso garantiza que puede usar alternativas de API para destinos específicos de .NET Framework en los casos donde .NET Core no admite una API determinada.

3. Use el [Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md) para analizar los ensamblados y desarrollar un plan para realizar la portabilidad en función de los resultados.

   Esta herramienta analiza los ensamblados compilados y genera un informe que muestra un resumen de portabilidad general, junto con un desglose de cada API que usa que no está disponible en .NET Core. Puede usar este informe junto con un análisis de su código base para desarrollar un plan de cómo portar el código.

4. Porte el código de prueba.

   Dado que portar a .NET Core es un cambio tan considerable para el código base, se recomienda encarecidamente portar las pruebas de forma que pueda ejecutarlas mientras porta el código. MSTest, xUnit y NUnit admiten .NET Core.

5. Ejecute el plan de portabilidad.

## <a name="tools-to-help"></a>Herramientas de ayuda

En la lista siguiente se muestran las herramientas que puede resultarle útiles durante el proceso de portabilidad:

* Api Portability Analyzer: [herramienta de línea de comandos](https://github.com/Microsoft/dotnet-apiport/releases) o [Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b), una cadena de herramientas que puede generar un informe de lo portátil que es su código entre .NET Framework y .NET Core, con un desglose de problemas ensamblado por ensamblado. Para más información, consulte [Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md).
* Analizador de API en .NET: un analizador de Roslyn que detecta posibles riesgos de compatibilidad de las API de C# en distintas plataformas y detecta llamadas a API en desuso. Para más información, consulte [Analizador de API en .NET](../../standard/analyzers/api-analyzer.md).
* Reverse Package Search: un [servicio web útil](https://packagesearch.azurewebsites.net) que le permite buscar un tipo y encontrar los paquetes que lo contienen.

Además, puede intentar portar soluciones más pequeñas o proyectos individuales en el formato de archivo de proyecto de .NET Core con la herramienta [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017).

> [!WARNING] 
> CsprojToVs2017 es una herramienta de terceros. No hay ninguna garantía de que funcione con todos los proyectos, y podría provocar cambios sutiles de comportamiento de los que dependa. CsprojToVs2017 debe usarse como _punto de partida_ que automatiza los elementos básicos que se pueden automatizar. No es una solución que se garantice para migrar formatos de archivo de proyecto.

>[!div class="step-by-step"]
>[Siguiente](third-party-deps.md)
