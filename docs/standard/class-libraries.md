---
title: Bibliotecas de clases de .NET
description: Obtenga información sobre cómo las bibliotecas de clase de .NET le permiten agrupar funcionalidades útiles en módulos que pueden usar varias aplicaciones.
author: richlander
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: a67484c3-fe92-44d8-8fa3-36fa2071d880
ms.openlocfilehash: e2fd0237556f877af64708674f00e9efddf95869
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209648"
---
# <a name="net-class-libraries"></a>Bibliotecas de clases de .NET

Las bibliotecas de clases son el concepto de [biblioteca compartida](https://en.wikipedia.org/wiki/Library_%28computing%29#Shared_libraries) de .NET. Le permiten dividir funcionalidades útiles en módulos que pueden usar varias aplicaciones. También se pueden usar para cargar la funcionalidad no necesaria o no conocida al inicio de la aplicación. Las bibliotecas de clases se describen mediante el [formato de archivo de Ensamblado de .NET](assembly/file-format.md).

Hay tres tipos de bibliotecas de clases que puede usar:

* Las bibliotecas de clases **específicas de la plataforma** tienen acceso a todas las API de una plataforma determinada (por ejemplo, .NET Framework, Xamarin iOS), pero solo las pueden usar las aplicaciones y bibliotecas destinadas a esa plataforma.
* Las bibliotecas de clases **portables** tienen acceso a un subconjunto de API y las pueden usar las aplicaciones y bibliotecas que tienen como destino varias plataformas.
* Las bibliotecas de clases de **.NET Standard** son una fusión del concepto de biblioteca específica de la plataforma y portable en un único modelo que ofrece lo mejor de ambas.

## <a name="platform-specific-class-libraries"></a>Bibliotecas de clases específicas de la plataforma

Las bibliotecas específicas de la plataforma se enlazan a una única implementación de .NET (por ejemplo, .NET Framework en Windows) y, por tanto, pueden tomar dependencias significativas de un entorno de ejecución conocido. Este entorno expondrá un conjunto conocido de API (API de .NET y SO) y mantendrán y expondrán el estado esperado (por ejemplo, Registro de Windows).

Los desarrolladores que creen bibliotecas específicas de la plataforma pueden aprovechar al máximo la plataforma subyacente. Las bibliotecas solo se ejecutarán en esa plataforma determinada, por lo que las comprobaciones de plataforma u otras formas de código condicional son innecesarios (código de abastecimiento único de módulo para varias plataformas).

Las bibliotecas específicas de la plataforma han sido el tipo de biblioteca de clases principal de .NET Framework. Incluso con la aparición de otras implementaciones de .NET, las bibliotecas específicas de la plataforma continúan siendo el tipo de biblioteca dominante.

## <a name="portable-class-libraries"></a>Bibliotecas de clases portables

Las bibliotecas portables son compatibles con varias implementaciones de .NET. Pueden tomar dependencias en un entorno de ejecución conocido; en cambio, el entorno es sintético y está generado por la intersección de un conjunto de implementaciones concretas de .NET. Las hipótesis de plataforma y API expuestas son un subconjunto de lo que estaría disponible para una biblioteca específica de la plataforma.

Puede elegir una configuración de plataforma al crear una biblioteca portable. La configuración de plataforma es el conjunto de plataformas que tiene que admitir (por ejemplo, .NET Framework 4.5+, Windows Phone 8.0+). Cuantas más plataformas decida admitir, menos API y menos hipótesis de plataforma puede hacer, el mínimo común denominador. Esta característica puede ser confusa al principio, ya que la gente suele pensar que "más es mejor", pero más plataformas compatibles suponen menos API disponibles.

Muchos desarrolladores de bibliotecas han pasado de producir bibliotecas específicas de varias plataformas de un origen (con las directivas de compilación condicionales) a bibliotecas portables. Hay [varios enfoques](https://blog.stephencleary.com/2012/11/portable-class-library-enlightenment.html) para acceder a la funcionalidad específica de la plataforma en las bibliotecas portables con bait-and-switch como la técnica más aceptada en este momento.

## <a name="net-standard-class-libraries"></a>Bibliotecas de clases .NET Standard

Las bibliotecas de .NET Standard son un reemplazo de los conceptos de bibliotecas específicas de la plataforma y portables. Son específicas de la plataforma ya que exponen toda la funcionalidad de la plataforma subyacente (sin plataformas sintéticas ni intersecciones de plataforma). Son portables ya que funcionan en todas las plataformas compatibles.

.NET Standard expone un conjunto de _contratos_ de bibliotecas. Las implementaciones de .NET deben admitir cada contrato por completo o no admitirlo. Cada implementación, por tanto, admite un conjunto de contratos de .NET Standard. Como consecuencia, cada biblioteca de clases de .NET Standard es compatible con las plataformas que admiten sus dependencias del contrato.

.NET Standard no expone toda la funcionalidad de .NET Framework (ni es un objetivo); en cambio, expone muchas más API que las bibliotecas de clases portables. Se agregarán más API con el tiempo.

Las siguientes plataformas admiten las bibliotecas de .NET Standard:

* .NET Core
* .NET Framework
* Mono
* Xamarin.iOS, Xamarin.Mac, Xamarin.Android
* Plataforma universal de Windows (UWP)
* Windows
* Windows Phone
* Windows Phone Silverlight

Para más información, consulte [.NET Standard](net-standard.md).

## <a name="mono-class-libraries"></a>Bibliotecas de clases de Mono

Las bibliotecas de clases se admiten en Mono, incluidos los tres tipos de bibliotecas que se han descrito anteriormente. A menudo, Mono se considera (correctamente) como una implementación multiplataforma de .NET Framework. En parte, se debía a que las bibliotecas de .NET Framework específicas de la plataforma podrían ejecutarse en el tiempo de ejecución Mono sin modificarse ni volver a compilarse. Esta característica ya existía antes de la creación de las bibliotecas de clases portables, por lo que era una elección obvia para habilitar la portabilidad binaria entre .NET Framework y Mono (aunque solo funcionaba en una dirección).
