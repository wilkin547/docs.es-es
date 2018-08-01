---
title: Controlar valores nulos en expresiones de consulta (LINQ en C#)
description: Obtenga información sobre cómo controlar valores nulos en expresiones de consulta de LINQ en C#.
ms.date: 12/1/2016
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.openlocfilehash: 34cda0be5fa38422415b6c3927f40a0df95fc6a6
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404108"
---
# <a name="handle-null-values-in-query-expressions"></a>Controlar valores nulos en expresiones de consulta

En este ejemplo se muestra cómo controlar los posibles valores nulos en colecciones de origen. Una colección de objetos como <xref:System.Collections.Generic.IEnumerable%601> puede contener elementos cuyo valor es [NULL](../language-reference/keywords/null.md). Si una colección de origen es nula o contiene un elemento cuyo valor es NULL, y la consulta no controla los valores NULL, se iniciará una <xref:System.NullReferenceException> cuando se ejecute la consulta.

## <a name="example"></a>Ejemplo

Se pueden codificar de forma defensiva para evitar una excepción de referencia nula, tal y como se muestra en el ejemplo siguiente:

[!code-csharp[csProgGuideLINQ#82](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]

En el ejemplo anterior, la cláusula `where` filtra todos los elementos nulos de la secuencia de categorías. Esta técnica es independiente de la comprobación de null en la cláusula join. La expresión condicional con null de este ejemplo funciona porque `Products.CategoryID` es de tipo `int?`, que es una abreviatura de `Nullable<int>`.

## <a name="example"></a>Ejemplo

En una cláusula join, si solo una de las claves de comparación es un tipo que acepta valores NULL, puede convertir la otra en un tipo que acepta valores NULL en la expresión de consulta. En el ejemplo siguiente, suponga que `EmployeeID` es una columna que contiene valores de tipo `int?`:

[!code-csharp[csProgGuideLINQ#83](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]

## <a name="see-also"></a>Vea también

<xref:System.Nullable%601>  
[Language-Integrated Query (LINQ)](index.md)  
[Nullable types](../programming-guide/nullable-types/index.md) (Tipos que aceptan valores NULL [Guía de programación de C#])  
