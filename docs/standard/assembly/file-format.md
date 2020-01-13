---
title: Formato de archivo de ensamblado .NET
description: Obtenga información sobre el formato de archivo de ensamblado .NET, que se usa para describir y contiene las bibliotecas y aplicaciones de .NET.
author: richlander
ms.date: 08/20/2019
ms.technology: dotnet-standard
ms.assetid: 6520323e-ff28-4c8a-ba80-e64a413199e6
ms.openlocfilehash: 4cf6522d66d7a1efccde45078768a773db6e6cb0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711589"
---
# <a name="net-assembly-file-format"></a>Formato de archivo de ensamblado .NET

.NET define un formato de archivo binario *ensamblado* que se usa para describir por completo y contener programas de .NET. Los ensamblados se usan para los programas, así como para las bibliotecas dependientes. Un programa de .NET se puede ejecutar como uno de varios ensamblados, no se necesitan otros artefactos, además de la implementación de .NET adecuada. Las dependencias nativas, incluidas las API del sistema operativo, constituyen un asunto independiente y no se incluyen en el formato de ensamblado. NET, aunque a veces se describen con este formato (por ejemplo, WinRT).

> Cada componente de CLI incluye los metadatos para las declaraciones, implementaciones y referencias específicas a ese componente. Por tanto, los metadatos específicos del componente se conocen como metadatos del componente y se dice que el componente resultante es autodescriptivo (de ECMA 335 I.9.1, Componentes y ensamblados).

El formato se especifica y estandariza por completo como [ECMA 335](https://www.ecma-international.org/publications/standards/Ecma-335.htm). Todos los compiladores y tiempos de ejecución de .NET usan este formato. La presencia de un formato binario documentado y actualizado con poca frecuencia ha sido una ventaja importante (posiblemente un requisito) para la interoperabilidad. El formato se ha actualizado por última vez de forma significativa en 2005 (.NET 2.0) para dar cabida a la arquitectura del procesador y genéricos.

El formato es independiente de la CPU y del sistema operativo. Se ha usado como parte de las implementaciones de .NET que se dirigen a muchos chips y CPU. Aunque el propio formato tiene legado de Windows, se puede implementar en cualquier sistema operativo. Posiblemente, la opción más importante para la interoperabilidad del sistema operativo es que la mayoría de los valores se almacenan en formato little-endian. No tiene una afinidad específica con el tamaño del puntero de equipo (por ejemplo, 32 bits, 64 bits).

El formato de ensamblado .NET también es muy descriptivo sobre la estructura de un programa o biblioteca determinados. Describe los componentes internos de un ensamblado, específicamente: referencias a ensamblados, tipos definidos y su estructura interna. Las herramientas o API pueden leer y procesar esta información para representarla o para tomar decisiones de programación.

## <a name="format"></a>Formato

El formato binario de .NET se basa en el formato de [archivo PE](https://en.wikipedia.org/wiki/Portable_Executable) de Windows. De hecho, las bibliotecas de clases de .NET son compatibles con Windows PE y, a primera vista, parecen ser bibliotecas de vínculos dinámicos (DLL) o aplicaciones ejecutables (EXE) de Windows. Se trata de una característica muy útil en Windows, donde pueden hacerse pasar por archivos binarios ejecutables nativos y recibir el mismo tratamiento (por ejemplo, carga del sistema operativo, herramientas de PE).

![Encabezados de ensamblado](../media/assembly-format/assembly-headers.png)

Encabezados de ensamblado de ECMA 335 II.25.1, Estructura del formato de archivo en tiempo de ejecución.

## <a name="process-the-assemblies"></a>Procesamiento de los ensamblados

Se pueden escribir herramientas o API para procesar ensamblados. La información de ensamblado permite tomar decisiones mediante programación en tiempo de ejecución, volver a escribir ensamblados, proporcionar API IntelliSense en un editor y generar documentación. <xref:System.Reflection?displayProperty=nameWithType>, <xref:System.Reflection.MetadataLoadContext?displayProperty=nameWithType> y [Mono.Cecil](https://www.mono-project.com/docs/tools+libraries/libraries/Mono.Cecil/) son buenos ejemplos de herramientas que se usan con frecuencia con este propósito.
