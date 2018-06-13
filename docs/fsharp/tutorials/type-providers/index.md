---
title: Proveedores de tipos
description: 'Obtenga información acerca de cómo un proveedor de tipo de F # es un componente que proporciona tipos, propiedades y métodos para su uso en los programas.'
ms.date: 04/02/2018
ms.openlocfilehash: 82d9afed7d77eae5f8b96854d40e96a32c4fae9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562275"
---
# <a name="type-providers"></a>Proveedores de tipos

Un proveedor de tipos de F# es un componente que proporciona tipos, propiedades y métodos para usar en el programa. Los proveedores de tipo generan lo que se conoce como **proporciona tipos**, que son generadas por el compilador de F # y se basan en un origen de datos externo.

Por ejemplo, un proveedor de tipo de F # para SQL puede generar tipos que representan tablas y columnas de una base de datos relacional. De hecho, esto es lo que la [SQLProvider](https://fsprojects.github.io/SQLProvider/) proveedor de tipo no.

Proporciona que tipos dependen de los parámetros de entrada a un proveedor de tipos. Dicha entrada puede ser un origen de datos de ejemplo (por ejemplo, un archivo de esquema JSON), una dirección URL que apunta directamente a un servicio externo o una cadena de conexión a un origen de datos. Un proveedor de tipos también puede asegurarse de que solo se expandan grupos de tipos a petición; es decir, que se expandan si realmente se hace referencia a los tipos de programa. Esto permite la integración directa a petición de espacios de información a gran escala, tales como mercados de datos en línea de forma fuertemente tipada.

## <a name="generative-and-erased-type-providers"></a>Proveedores de tipos generativa y borrados

Los proveedores de tipo tienen dos formas: Generativa y borrados.

Los proveedores de tipos generativa generar tipos que se pueden escribir como tipos de .NET en el ensamblado en el que se generan. Esto les permite a ser consumidos desde el código de otros ensamblados. Esto significa que la representación del origen de datos con tipo generalmente debe ser uno que sea adecuado para representar con tipos de .NET.

Los proveedores de tipo borrado producen tipos que solo se puede utilizar en el ensamblado o proyecto que se generan desde. Los tipos son efímeros; es decir, que no se escriben en un ensamblado y no pueden ser utilizados por código de otros ensamblados. Pueden contener *retrasa* miembros, lo que le permite utilizar proporciona tipos de un espacio de información potencialmente infinita. Son útiles para el uso de un pequeño subconjunto de un origen de datos de gran tamaño y conectadas entre sí.

## <a name="commonly-used-type-providers"></a>Los proveedores de tipo de uso frecuente

Las siguientes bibliotecas usados contienen proveedores de tipos para usos diferentes:

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) incluye proveedores de tipo de documento HTML, XML, CSV y JSON formatos y los recursos.
- [SQLProvider](https://fsprojects.github.io/SQLProvider/) proporciona acceso fuertemente tipado para bases de datos de relación mediante la asignación de objetos y LINQ de F # las consultas realizadas en estos orígenes de datos.
- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) un conjunto de proveedores de tipo de tiempo de compilación buscó incrustación de T-SQL en F #.
- [El proveedor de tipo de almacenamiento Azure](https://fsprojects.github.io/AzureStorageTypeProvider/) proporciona tipos para Blobs de Azure, tablas y colas, lo que le permite tener acceso a estos recursos sin necesidad de especificar los nombres de recursos como cadenas en todo el programa.
- [FSharp.Data.GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html) contiene el **GraphQLProvider**, que proporciona tipos basados en un servidor de GraphQL especificado por la dirección URL.

En caso necesario, puede [crear sus propios proveedores de tipo personalizado](creating-a-type-provider.md), o hacer referencia a proveedores de tipos que se han creado por otros usuarios. Por ejemplo, suponga que su organización tiene un servicio de datos que proporciona un número elevado y creciente de conjuntos de datos con nombre, cada uno con su propio esquema de datos estable. Se puede elegir crear un proveedor de tipo que lea los esquemas y presente los últimos conjuntos de datos disponibles al programador de forma fuertemente tipada.

## <a name="see-also"></a>Vea también
[Tutorial: Crear un proveedor de tipos](creating-a-type-provider.md)

[Referencia del lenguaje F#](../../language-reference/index.md)

[Visual F#](../../index.md)
