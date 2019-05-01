---
title: Proveedores de tipos
description: Obtenga información sobre cómo un F# proveedor de tipos es un componente que proporciona tipos, propiedades y métodos para su uso en los programas.
ms.date: 04/02/2018
ms.openlocfilehash: 39000fd1ca2af78afd1c333816fe9d5c0e2517cb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967770"
---
# <a name="type-providers"></a>Proveedores de tipos

Un proveedor de tipos de F# es un componente que proporciona tipos, propiedades y métodos para usar en el programa. Los proveedores de tipos generan lo que se conoce como **proporciona tipos**, que son generados por el F# compilador y se basan en un origen de datos externo.

Por ejemplo, un F# proveedor de tipos para SQL puede generar tipos que representan las tablas y columnas en una base de datos relacional. De hecho, esto es lo que el [SQLProvider](https://fsprojects.github.io/SQLProvider/) hace el proveedor de tipo.

Proporciona que tipos dependen de los parámetros de entrada a un proveedor de tipos. Dicha entrada puede ser un origen de datos de ejemplo (por ejemplo, un archivo de esquema JSON), una dirección URL que apunta directamente a un servicio externo o una cadena de conexión a un origen de datos. Un proveedor de tipos también puede asegurarse de que solo se expanden los grupos de tipos a petición; es decir, que se expandan si realmente se hace referencia a los tipos en los programas. Esto permite la integración directa a petición de espacios de información a gran escala, tales como mercados de datos en línea de forma fuertemente tipada.

## <a name="generative-and-erased-type-providers"></a>Proveedores de tipos generativa y borrados

Los proveedores de tipos se dividen en dos formas: Generativa y borrados.

Los proveedores de tipos generativa generar tipos que se pueden escribir como tipos de .NET en el ensamblado en la que se generan. Esto les permite consumir desde el código de otros ensamblados. Esto significa que la representación del origen de datos con tipo generalmente debe ser uno que sea posible para representar con tipos de. NET.

Borrado de los proveedores de tipos producen tipos que sólo pueden utilizarse en el ensamblado o proyecto que se generan a partir. Los tipos son efímeros; es decir, que no se escriben en un ensamblado y no pueden usarse por código de otros ensamblados. Pueden contener *retrasa* miembros, lo que le permite utilizar proporcionado tipos de un espacio de información potencialmente infinito. Son útiles para el uso de un pequeño subconjunto de un origen de datos de gran tamaño e interconectadas.

## <a name="commonly-used-type-providers"></a>Los proveedores de tipos de uso frecuente

Las siguientes bibliotecas usados contienen los proveedores de tipos para usos diferentes:

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) incluye proveedores de tipos de recursos y formatos de documento HTML, XML, CSV y JSON.
- [SQLProvider](https://fsprojects.github.io/SQLProvider/) proporciona acceso fuertemente tipado para las bases de datos de relación mediante la asignación de objeto y F# consultas LINQ en estos orígenes de datos.
- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) ha comprobado un conjunto de proveedores de tipo de tiempo de compilación de inserción de T-SQL en F#.
- [El proveedor de tipo de almacenamiento Azure](https://fsprojects.github.io/AzureStorageTypeProvider/) proporciona tipos para Azure Blobs, tablas y colas, lo que permite tener acceso a estos recursos sin necesidad de especificar los nombres de recursos como cadenas a lo largo de su programa.
- [FSharp.Data.GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html) contiene el **GraphQLProvider**, que proporciona tipos basados en un servidor GraphQL especificado por la dirección URL.

En caso necesario, puede [crear sus propios proveedores de tipo personalizado](creating-a-type-provider.md), o hacer referencia a los proveedores de tipos que se han creado otros usuarios. Por ejemplo, suponga que su organización tiene un servicio de datos que proporciona un número elevado y creciente de conjuntos de datos con nombre, cada uno con su propio esquema de datos estable. Se puede elegir crear un proveedor de tipo que lea los esquemas y presente los últimos conjuntos de datos disponibles al programador de forma fuertemente tipada.

## <a name="see-also"></a>Vea también

- [Tutorial: Crear un proveedor de tipos](creating-a-type-provider.md)
- [Referencia del lenguaje F#](../../language-reference/index.md)
- [Visual F#](../../index.md)