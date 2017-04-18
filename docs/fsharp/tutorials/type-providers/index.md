---
title: Proveedores de tipos
description: Proveedores de tipos
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 25697ef6-465e-4248-9de5-1d199d4a8b59
translationtype: Human Translation
ms.sourcegitcommit: 0a01ec92a90d99fafaacbd3f71f5177e5cf94a68
ms.openlocfilehash: e9e67e6531e0c1daad0c0d4a9f778670d5cb2263
ms.lasthandoff: 04/05/2017

---

# <a name="type-providers"></a>Proveedores de tipos

> [!NOTE]
Esta guía se escribió para F# 3.0 y se actualizará.  Vea [FSharp.Data](http://fsharp.github.io/FSharp.Data/) para obtener información sobre los proveedores de tipos multiplataforma actualizados.

Un proveedor de tipos de F# es un componente que proporciona tipos, propiedades y métodos para usar en el programa. Los proveedores de tipo son una parte importante de la compatibilidad de F# 3.0 con la programación con amplio acceso a diferentes fuentes de información. La clave para este tipo de programación es eliminar las barreras para trabajar con las distintas fuentes de información que se encuentran en Internet y en los entornos empresariales modernos. Una barrera importante para incluir una fuente de información en un programa es la necesidad de representar dicha información como tipos, propiedades y métodos para usarlos en un entorno de lenguaje de programación. La escritura manual de estos tipos lleva mucho tiempo y es difícil de mantener. Una alternativa común es usar un generador de código que agregue archivos al proyecto. Sin embargo, los tipos convencionales de generación de código no se integran bien en los modos exploratorios de programación admitidos por F#, puesto que el código generado debe reemplazarse cada vez que se ajuste una referencia de servicio.

Los tipos proporcionados por los proveedores de tipo de F# normalmente se basan en fuentes de información externas. Por ejemplo, un proveedor de tipo de F# para SQL proporcionará los tipos, propiedades y métodos necesarios para trabajar directamente con las tablas de cualquier base de datos SQL a la que se tenga acceso. De igual forma, un proveedor de tipo para los servicios Web WSDL proporcionará los tipos, propiedades y métodos necesarios para trabajar directamente con cualquier servicio Web WSDL.

El conjunto de tipos, propiedades y métodos proporcionados por un proveedor de tipo de F# puede depender de los parámetros especificados en el código del programa. Por ejemplo, un proveedor de tipo puede proporcionar diferentes tipos en función de una cadena de conexión o de una dirección URL de servicio. De este modo, el espacio de información disponible por medio de una cadena de conexión o dirección URL se integra directamente en el programa. Un proveedor de tipo también puede asegurar que solo se expandan grupos de tipos a petición, es decir, que se expandan si el programa hace realmente referencia a los tipos. Esto permite la integración directa a petición de espacios de información a gran escala, tales como mercados de datos en línea de forma fuertemente tipada.

F# contiene varios proveedores de tipo integrados para servicios de datos empresariales y de Internet de uso habitual. Estos proveedores de tipo proporcionan acceso simple y regular a bases de datos relacionales SQL y a servicios basados en red de tipo OData y WSDL y admiten el uso de consultas LINQ de F# en estos orígenes de datos.

En caso necesario, se pueden crear proveedores de tipo personalizados propios o se puede hacer referencia a proveedores de tipo creados por otros. Por ejemplo, suponga que su organización tiene un servicio de datos que proporciona un número elevado y creciente de conjuntos de datos con nombre, cada uno con su propio esquema de datos estable. Se puede elegir crear un proveedor de tipo que lea los esquemas y presente los últimos conjuntos de datos disponibles al programador de forma fuertemente tipada.


## <a name="related-topics"></a>Temas relacionados


|Título|Descripción|
|-----|-----------|
|[Tutorial: Acceso a una base de datos SQL mediante proveedores de tipos](accessing-a-sql-database.md)|Explica cómo usar el proveedor de tipos SqlDataConnection para tener acceso a las tablas y los procedimientos almacenados de una base de datos SQL, basándose en una cadena de conexión para una conexión directa con una base de datos. El acceso usa una asignación de LINQ to SQL.|
|[Tutorial: Acceso a una base de datos SQL mediante proveedores de tipo y entidades](accessing-a-sql-database-entities.md)|Explica cómo usar el proveedor de tipos SqlEntityConnection para tener acceso a las tablas y los procedimientos almacenados de una base de datos SQL, basándose en una cadena de conexión para una conexión directa con una base de datos. El acceso usa una asignación de LINQ a Entities. Este método funciona con cualquier base de datos, pero en el ejemplo mostrado se usa SQL Server.|
|[Tutorial: Acceso a un servicio OData mediante proveedores de tipos](accessing-an-odata-service.md)|Explica cómo usar el proveedor de tipos ODataService para tener acceso a un servicio OData de forma fuertemente tipada en función de una dirección URL de servicio.|
|[Tutorial: Acceso a un servicio web mediante proveedores de tipos](accessing-a-web-service.md)|Explica cómo usar el proveedor de tipos WsdlService para tener acceso a un servicio Web WSDL de forma fuertemente tipada en función de una dirección URL de servicio.|
|[Tutorial: Generar tipos en F&#35; a partir de un archivo DBML](generating-fsharp-types-from-dbml.md)|Explica cómo usar el proveedor de tipos DbmlFile para tener acceso a las tablas y los procedimientos almacenados de una base de datos SQL, en función de un archivo DBML que proporciona una especificación de esquema de base de datos LINQ to SQL.|
|[Tutorial: Generar tipos en F&#35; a partir de un archivo de esquema EDMX](generating-fsharp-types-from-edmx.md)|Explica cómo usar el proveedor de tipos EdmxFile para tener acceso a las tablas y los procedimientos almacenados de una base de datos SQL, en función de un archivo EDMX que proporciona una especificación de esquema de Entity Framework.|
|[Tutorial: Crear un proveedor de tipos](creating-a-type-provider.md)|Proporciona información sobre cómo escribir proveedores de tipo personalizados propios.|
|[Seguridad del proveedor de tipos](type-provider-security.md)|Proporciona información sobre cuestiones de seguridad que se deben tener en cuenta al desarrollar proveedores de tipos.|
|[Solución de problemas en proveedores de tipos](troubleshooting-type-providers.md)|Proporciona información sobre problemas habituales que pueden surgir cuando se trabaja con proveedores de tipos e incluye sugerencias para soluciones.|

## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](../../language-reference/index.md)

[Visual F#](../../index.md)
