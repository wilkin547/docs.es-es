---
title: Bibliotecas de Framework
description: Obtenga información sobre cómo las bibliotecas proporcionan implementaciones para muchos tipos generales y específicos de las aplicaciones, algoritmos y funcionalidad de la utilidad.
author: richlander
ms.date: 06/20/2016
ms.assetid: 7b77b6c1-8367-4602-bff3-91e4c05ac643
ms.openlocfilehash: 4e71f81b0dd72f4569d8b6b319b9e97491533d28
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96438204"
---
# <a name="framework-libraries"></a>Bibliotecas de Framework

.NET tiene un amplio conjunto estándar de bibliotecas, a las que se hace referencia como bibliotecas de clases base (conjunto básico) o bibliotecas de clases de marco de trabajo (conjunto completo). Estas bibliotecas proporcionan implementaciones para muchos tipos generales y específicos de las aplicaciones, algoritmos y funcionalidad de la utilidad. Las bibliotecas comerciales y las comunitarias se basan en las bibliotecas de clases de marco de trabajo, ya que ofrecen bibliotecas estándar fáciles de usar para un amplio conjunto de tareas informáticas.

Se proporcionan un subconjunto de estas bibliotecas con cada implementación .NET. Se esperan API de bibliotecas de clases base (BCL) con cualquier implementación de .NET porque los programadores las querrán y porque las bibliotecas populares necesitarán su ejecución. No estarán disponibles bibliotecas específicas de la aplicación por encima de BCL, como ASP.NET, en todas las implementaciones .NET.

## <a name="base-class-libraries"></a>Bibliotecas de clases base

La BCL proporciona los tipos más fundamentales y la funcionalidad de la utilidad, además de ser la base de otras bibliotecas de clases .NET. Pretende ofrecer implementaciones muy generales sin compensaciones por ninguna carga de trabajo. El rendimiento es siempre una consideración importante, puesto que las aplicaciones podrían preferir una directiva concreta, como baja latencia para alto rendimiento o baja memoria para uso bajo de la CPU. Estas bibliotecas están diseñadas para ser generalmente de alto rendimiento y adoptar un enfoque de término medio atendiendo a estos diferentes aspectos de rendimiento. En la mayoría de las aplicaciones, este enfoque ha tenido bastante éxito.

## <a name="primitive-types"></a>Tipos primitivos

.NET incluye un conjunto de tipos primitivos, que se usan (en distintos grados) en todos los programas. Estos tipos contienen datos, como números, cadenas, bytes y objetos arbitrarios. El lenguaje C# incluye palabras clave para estos tipos. A continuación se muestra un conjunto de ejemplo de estos tipos, con las palabras clave de C# correspondientes.

* <xref:System.Object?displayProperty=nameWithType> ([object](../csharp/language-reference/builtin-types/reference-types.md#the-object-type)): la clase base fundamental en el sistema de tipos de CLR. Es la raíz de la jerarquía de tipos.
* <xref:System.Int16?displayProperty=nameWithType> ([short](../csharp/language-reference/builtin-types/integral-numeric-types.md)): tipo entero con signo de 16 bits. También existe el valor <xref:System.UInt16> sin signo.
* <xref:System.Int32?displayProperty=nameWithType> ([int](../csharp/language-reference/builtin-types/integral-numeric-types.md)): tipo entero con signo de 32 bits. También existe el valor [UInt32](../csharp/language-reference/builtin-types/integral-numeric-types.md) sin firmar.
* <xref:System.Single?displayProperty=nameWithType> ([float](../csharp/language-reference/builtin-types/floating-point-numeric-types.md)): tipo de punto flotante de 32 bits.
* <xref:System.Decimal?displayProperty=nameWithType> ([decimal](../csharp/language-reference/builtin-types/floating-point-numeric-types.md)): tipo decimal de 128 bits.
* <xref:System.Byte?displayProperty=nameWithType> ([byte](../csharp/language-reference/builtin-types/integral-numeric-types.md)): entero sin signo de 8 bits que representa un byte de memoria.
* <xref:System.Boolean?displayProperty=nameWithType> ([bool](../csharp/language-reference/builtin-types/bool.md)): tipo booleano que representa `true` o `false`.
* <xref:System.Char?displayProperty=nameWithType> ([char](../csharp/language-reference/builtin-types/char.md)): tipo numérico de 16 bits que representa un carácter Unicode.
* <xref:System.String?displayProperty=nameWithType> ([string](../csharp/language-reference/builtin-types/reference-types.md#the-string-type)): representa una serie de caracteres. Diferente de `char[]`, pero permite la indexación en cada `char` individual en `string`.

## <a name="data-structures"></a>Estructuras de datos

.NET incluye un conjunto de estructuras de datos que son la piedra angular de casi cualquier aplicación .NET. Principalmente se trata de colecciones, pero también incluyen otros tipos.

* <xref:System.Array>: representa una matriz de objetos fuertemente tipados a la que se puede acceder por el índice. Tiene un tamaño fijo debido a su construcción.
* <xref:System.Collections.Generic.List%601>: representa una lista de objetos fuertemente tipados a la que se puede obtener acceso por índice. Cambia automáticamente de tamaño según sea necesario.
* <xref:System.Collections.Generic.Dictionary%602>: representa una colección de valores que se indexan mediante una clave. Se puede obtener acceso a los valores a través de la clave. Cambia automáticamente de tamaño según sea necesario.
* <xref:System.Uri>: proporciona una representación de objeto de un identificador uniforme de recursos (URI) y un acceso sencillo a las partes del identificador URI.
* <xref:System.DateTime>: representa un instante de tiempo, normalmente expresado en forma de fecha y hora del día.

## <a name="utility-apis"></a>API de utilidades

.NET incluye un conjunto de API de utilidades que proporcionan funcionalidad para muchas tareas importantes.

* <xref:System.Net.Http.HttpClient>: una API para enviar solicitudes HTTP y recibir respuestas HTTP de un recurso identificado por un URI.
* <xref:System.Xml.Linq.XDocument>: una API para cargar y consultar documentos XML con LINQ.
* <xref:System.IO.StreamReader>: una API para leer archivos.
* <xref:System.IO.StreamWriter>: una API para escribir archivos.

## <a name="app-model-apis"></a>API del modelo de aplicaciones

Hay muchos modelos de aplicaciones que pueden usarse con .NET, proporcionados por varias empresas.

* [ASP.NET](https://www.asp.net): proporciona un marco de trabajo web para la creación de sitios Web y servicios. Es compatible con Windows, Linux y macOS (depende de la versión de ASP.NET).
