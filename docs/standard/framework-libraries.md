---
title: Bibliotecas de Framework
description: Bibliotecas de Framework
keywords: .NET, .NET Core
author: richlander
ms.author: ronpet
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 7b77b6c1-8367-4602-bff3-91e4c05ac643
translationtype: Human Translation
ms.sourcegitcommit: 093b852fe1ed2307ebce914381fe47388b435c95
ms.openlocfilehash: c11f89522a97d60f5ffb8588f4500b64b5d2d6db

---

# <a name="framework-libraries"></a>Bibliotecas de Framework

.NET tiene un amplio conjunto estándar de bibliotecas, a las que se hace referencia como bibliotecas de clases base (conjunto básico) o bibliotecas de clases de marco de trabajo (conjunto completo). Estas bibliotecas proporcionan implementaciones para muchos tipos generales y específicos de las aplicaciones, algoritmos y funcionalidad de la utilidad. Las bibliotecas comerciales y las comunitarias se basan en las bibliotecas de clases de marco de trabajo, ya que ofrecen bibliotecas estándar fáciles de usar para un amplio conjunto de tareas informáticas.

Se proporcionan un subconjunto de estas bibliotecas con cada implementación .NET. Se esperan API de bibliotecas de clases base (BCL) con cualquier implementación de .NET porque los programadores las querrán y porque las bibliotecas populares necesitarán su ejecución. No estarán disponibles bibliotecas específicas de la aplicación por encima de BCL, como ASP.NET, en todas las implementaciones .NET.

## <a name="base-class-libraries"></a>Bibliotecas de clases base

La BCL proporciona los tipos más fundamentales y la funcionalidad de la utilidad, además de ser la base de otras bibliotecas de clases .NET. Pretende ofrecer implementaciones muy generales sin compensaciones por ninguna carga de trabajo. El rendimiento es siempre una consideración importante, puesto que las aplicaciones podrían preferir una directiva concreta, como baja latencia para alto rendimiento o baja memoria para uso bajo de la CPU. Estas bibliotecas están diseñadas para ser generalmente de alto rendimiento y adoptar un enfoque de término medio atendiendo a estos diferentes aspectos de rendimiento. En la mayoría de las aplicaciones, este enfoque ha tenido bastante éxito.

## <a name="primitive-types"></a>Tipos primitivos

.NET incluye un conjunto de tipos primitivos, que se usan (en distintos grados) en todos los programas. Estos tipos contienen datos, como números, cadenas, bytes y objetos arbitrarios. El lenguaje C# incluye palabras clave para estos tipos. A continuación se muestra un conjunto de ejemplo de estos tipos, con las palabras clave de C# correspondientes.

*   [System.Object](https://msdn.microsoft.com/library/system.object.aspx) ([object](https://msdn.microsoft.com/library/9kkx3h3c.aspx)): la clase base fundamental en el sistema de tipos de CLR. Es la raíz de la jerarquía de tipos.
*   [System.Int16](https://msdn.microsoft.com/library/system.int16.aspx) ([short](https://msdn.microsoft.com/library/ybs77ex4.aspx)): tipo entero con firma de 16 bits. También existe el valor [UInt16](https://msdn.microsoft.com/library/system.uint16.aspx) sin firmar.
*   [System.Int32](https://msdn.microsoft.com/library/system.int32.aspx) ([int](https://msdn.microsoft.com/library/5kzh1b5w.aspx)): tipo entero con firma de 32 bits. También existe el valor [UInt32](https://msdn.microsoft.com/library/x0sksh43.aspx) sin firmar.
*   [System.Single](https://msdn.microsoft.com/library/system.single.aspx) ([float](https://msdn.microsoft.com/library/b1e65aza.aspx)): tipo de punto flotante de 32 bits.
*   [System.Decimal](https://msdn.microsoft.com/library/system.decimal.aspx) ([decimal](https://msdn.microsoft.com/library/364x0z75.aspx)): tipo decimal de 128 bits.
*   [System.Byte](https://msdn.microsoft.com/library/system.byte.aspx) ([byte](https://msdn.microsoft.com/library/5bdb6693.aspx)): entero sin firmar de 8 bits que representa un byte de memoria.
*   [System.Boolean](https://msdn.microsoft.com/library/system.boolean.aspx) ([bool](https://msdn.microsoft.com/library/c8f5xwh7.aspx)): tipo booleano que representa 'true' o 'false'.
*   [System.Char](https://msdn.microsoft.com/library/system.char.aspx) ([char](https://msdn.microsoft.com/library/x9h8tsay.aspx)): tipo numérico de 16 bits que representa un carácter Unicode.
*   [System.String](https://msdn.microsoft.com/library/system.string.aspx) ([string](https://msdn.microsoft.com/library/362314fe.aspx)): representa una serie de caracteres. Diferente de `char[]`, pero permite la indexación en cada `char` individual en `string`.

## <a name="data-structures"></a>Estructuras de datos

.NET incluye un conjunto de estructuras de datos que son la piedra angular de casi cualquier aplicación .NET. Principalmente se trata de colecciones, pero también incluyen otros tipos.

*   [Array](https://msdn.microsoft.com/library/system.array.aspx): representa una lista de objetos fuertemente tipados a la que se puede obtener acceso por índice. Tiene un tamaño fijo debido a su construcción.
*   [List](https://msdn.microsoft.com/library/6sh2ey19.aspx): representa una lista de objetos fuertemente tipados a la que se puede obtener acceso por índice. Cambia automáticamente de tamaño según sea necesario.
*   [Dictionary](https://msdn.microsoft.com/library/xfhwa508.aspx): representa una colección de valores que se indexan mediante una clave. Se puede obtener acceso a los valores a través de la clave. Cambia automáticamente de tamaño según sea necesario.
*   [Uri](https://msdn.microsoft.com/library/system.uri.aspx): proporciona una representación de objeto de un identificador de recursos uniforme (URI) y un acceso sencillo a las partes del identificador URI.
*   [DateTime](https://msdn.microsoft.com/library/system.datetime.aspx): representa un instante de tiempo, normalmente expresado en forma de fecha y hora del día.

## <a name="utility-apis"></a>API de utilidades

.NET incluye un conjunto de API de utilidades que proporcionan funcionalidad para muchas tareas importantes.

*   [HttpClient](https://msdn.microsoft.com/library/system.net.http.httpclient.aspx): una API para enviar solicitudes HTTP y recibir respuestas HTTP de un recurso identificado por un URI.
*   [XDocument](https://msdn.microsoft.com/library/system.xml.linq.xdocument.aspx): una API para cargar y consultar documentos XML con LINQ.
*   [StreamReader](https://msdn.microsoft.com/library/system.io.streamreader.aspx): una API para leer archivos Se puede usar ([StreamWriter](https://msdn.microsoft.com/library/system.io.stringwriter.aspx)) para escribir archivos.

## <a name="app-model-apis"></a>API del modelo de aplicaciones

Hay muchos modelos de aplicaciones que pueden usarse con .NET, proporcionados por varias empresas.

*   [ASP.NET](http://asp.net): proporciona un marco de trabajo web para la creación de sitios Web y servicios. Es compatible con Windows, Linux y macOS (depende de la versión de ASP.NET).



<!--HONumber=Nov16_HO3-->


