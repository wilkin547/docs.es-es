---
title: Proveedores de tipos
description: Obtenga información sobre F# cómo un proveedor de tipos es un componente que proporciona tipos, propiedades y métodos para su uso en los programas.
ms.date: 04/02/2018
ms.openlocfilehash: 7fa0ff6b5f2b0bc978df2988f22b2042acc22320
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552915"
---
# <a name="type-providers"></a>Proveedores de tipos

Un proveedor de tipos de F# es un componente que proporciona tipos, propiedades y métodos para usar en el programa. Los proveedores de tipos generan lo que se conoce como **tipos proporcionados**, que F# son generados por el compilador y se basan en un origen de datos externo.

Por ejemplo, un F# proveedor de tipo para SQL puede generar tipos que representan tablas y columnas en una base de datos relacional. De hecho, esto es lo que hace el proveedor de tipo [SQLProvider](https://fsprojects.github.io/SQLProvider/) .

Los tipos proporcionados dependen de los parámetros de entrada de un proveedor de tipo. Dicha entrada puede ser un origen de datos de ejemplo (como un archivo de esquema JSON), una dirección URL que apunta directamente a un servicio externo o una cadena de conexión a un origen de datos. Un proveedor de tipo también puede asegurarse de que los grupos de tipos solo se expandan a petición. es decir, se expanden si el programa hace realmente referencia a los tipos. Esto permite la integración directa a petición de espacios de información a gran escala, tales como mercados de datos en línea de forma fuertemente tipada.

## <a name="generative-and-erased-type-providers"></a>Proveedores de tipos generados y generados

Los proveedores de tipos tienen dos formas: generable y borrado.

Los proveedores de tipo informativo producen tipos que se pueden escribir como tipos .NET en el ensamblado en el que se generan. Esto permite que se consuman desde el código de otros ensamblados. Esto significa que la representación con tipo del origen de datos debe ser, por lo general, una que sea factible representar con tipos .NET.

Los proveedores de tipo de borrado producen tipos que solo se pueden consumir en el ensamblado o proyecto desde el que se generan. Los tipos son efímeros; es decir, no se escriben en un ensamblado y no se pueden usar en el código de otros ensamblados. Pueden contener miembros *retrasados* , lo que le permite usar tipos proporcionados a partir de un espacio de información potencialmente infinito. Son útiles para usar un pequeño subconjunto de un origen de datos grande e interconectado.

## <a name="commonly-used-type-providers"></a>Proveedores de tipos usados comúnmente

Las siguientes bibliotecas de uso generalizado contienen proveedores de tipos para diferentes usos:

- [FSharp. Data](https://fsharp.github.io/FSharp.Data/) incluye proveedores de tipos para los formatos y recursos de los documentos JSON, XML, csv y HTML.
- [SQLProvider](https://fsprojects.github.io/SQLProvider/) proporciona acceso fuertemente tipado a las bases de datos de relaciones a través de F# la asignación de objetos y las consultas LINQ en estos orígenes de datos.
- [FSharp. Data. SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) tiene un conjunto de proveedores de tipo para la incrustación comprobada en tiempo de compilación F#de T-SQL en.
- [Azure Storage proveedor de tipos](https://fsprojects.github.io/AzureStorageTypeProvider/) proporciona tipos para blobs, tablas y colas de Azure, lo que le permite tener acceso a estos recursos sin necesidad de especificar nombres de recursos como cadenas en todo el programa.
- [FSharp. Data. GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html) contiene **GraphQLProvider**, que proporciona tipos basados en un servidor de GraphQL especificado por la dirección URL.

En caso necesario, puede [crear sus propios proveedores de tipos personalizados](creating-a-type-provider.md)o hacer referencia a proveedores de tipos creados por otros usuarios. Por ejemplo, suponga que su organización tiene un servicio de datos que proporciona un número elevado y creciente de conjuntos de datos con nombre, cada uno con su propio esquema de datos estable. Se puede elegir crear un proveedor de tipo que lea los esquemas y presente los últimos conjuntos de datos disponibles al programador de forma fuertemente tipada.

## <a name="see-also"></a>Vea también

- [Tutorial: crear un proveedor de tipos](creating-a-type-provider.md)
- [Referencia del lenguaje F#](../../language-reference/index.md)
