---
title: Proveedores de tipos
description: Obtenga más información sobre los proveedores de tipos de F#, un componente que proporciona tipos, propiedades y métodos para usar en los programas.
ms.date: 04/02/2018
ms.openlocfilehash: eae64d2e318ee93f0b8d5b91f0c6da6c91743527
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202107"
---
# <a name="type-providers"></a>Proveedores de tipos

Un proveedor de tipos de F# es un componente que proporciona tipos, propiedades y métodos para usar en el programa. Los proveedores de tipos ofrecen lo que se conoce como **tipos proporcionados**, que se generan mediante el compilador de F# y se basan en un origen de datos externo.

Por ejemplo, un proveedor de tipos de F# para SQL puede generar tipos que representen tablas y columnas en una base de datos relacional. De hecho, esto es lo que hace el proveedor de tipos [SQLProvider](https://fsprojects.github.io/SQLProvider/).

Los tipos proporcionados dependen de los parámetros de entrada para un proveedor de tipos. Dicha entrada puede ser un origen de datos de muestra (por ejemplo, archivo de esquema JSON), una dirección URL que apunte directamente a un servicio externo o una cadena de conexión a un origen de datos. Un proveedor de tipos también permite garantizar que solo se expandan grupos de tipos a petición, es decir, que se expandan si el programa realmente hace referencia a los tipos. Esto permite la integración directa a petición de espacios de información a gran escala, tales como mercados de datos en línea de forma fuertemente tipada.

## <a name="generative-and-erased-type-providers"></a>Proveedores de tipos generativos y de borrado

Hay dos clases de proveedores de tipos: generativos y de borrado.

Los proveedores de tipos generativos producen tipos que se pueden escribir como tipos de .NET en el ensamblado en el que se generan. Esto permite su consumo a partir de código en otros ensamblados. Esto significa que, en general, la representación tipada del origen de datos debe ser una factible para la representación con tipos de .NET.

Los proveedores de tipos de borrado producen tipos que solo se pueden consumir en el ensamblado o proyecto en el que se generan. Los tipos son efímeros, es decir, no se escriben en un ensamblado y no se pueden consumir mediante código en otros ensamblados. Pueden contener miembros *con retraso*, lo cual permite usar tipos proporcionados a partir de un espacio de información que sea potencialmente infinito. Son útiles para usar un subconjunto pequeño de un origen de datos grande e interconectado.

## <a name="commonly-used-type-providers"></a>Proveedores de tipos usados habitualmente

Las siguientes bibliotecas de uso generalizado contienen proveedores de tipos para diferentes usos:

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) incluye proveedores de tipos para recursos y formatos de documento JSON, XML, CSV y HTML.
- [SQLProvider](https://fsprojects.github.io/SQLProvider/) proporciona acceso fuertemente tipado a bases de datos relacionales a través de la asignación de objetos y consultas LINQ de F# en dichos orígenes de datos.
- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) tiene un conjunto de proveedores de tipos para la inserción comprobada en tiempo de compilación de T-SQL en F#.
- El [proveedor de tipos de Azure Storage](https://fsprojects.github.io/AzureStorageTypeProvider/) ofrece tipos para Azure Blobs, Tables y Queues, lo cual permite acceder a dichos recursos sin necesidad de especificar los nombres de los recursos como cadenas en todo el programa.
- [FSharp.Data.GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html) contiene **GraphQLProvider**, que proporciona tipos basados en un servidor GraphQL especificado mediante una dirección URL.

En los casos en los que sea necesario, se pueden [crear proveedores de tipos personalizados propios](creating-a-type-provider.md), o bien hacer referencia a proveedores de tipos creados por otros. Por ejemplo, suponga que su organización tiene un servicio de datos que proporciona un número elevado y creciente de conjuntos de datos con nombre, cada uno con su propio esquema de datos estable. Se puede elegir crear un proveedor de tipo que lea los esquemas y presente los últimos conjuntos de datos disponibles al programador de forma fuertemente tipada.

## <a name="see-also"></a>Vea también

- [Tutorial: Creación de un proveedor de tipos](creating-a-type-provider.md)
- [Referencia del lenguaje F#](../../language-reference/index.md)
