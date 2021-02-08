---
description: 'Más información acerca de: BC36593: la expresión de tipo <type> no es consultable'
title: No se puede consultar una expresión de tipo <type>
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: b2fc6c81ee34c1f8e251ac65ba582fde1c6a7b9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796358"
---
# <a name="bc36593-expression-of-type-type-is-not-queryable"></a>BC36593: la expresión de tipo \<type> no es consultable

La expresión de tipo \<type> no es consultable. Asegúrese de que no falta una referencia de ensamblado o una importación de espacio de nombres para el proveedor LINQ.

 Los tipos consultables se definen en <xref:System.Linq> los <xref:System.Data.Linq> espacios de <xref:System.Xml.Linq> nombres, y. Debe importar uno o varios de estos espacios de nombres para realizar consultas LINQ.

 El <xref:System.Linq> espacio de nombres permite consultar objetos como colecciones y matrices mediante Linq.

 El <xref:System.Data.Linq> espacio de nombres permite consultar conjuntos de datos de ADO.net y bases de datos de SQL Server mediante Linq.

 El <xref:System.Xml.Linq> espacio de nombres permite consultar XML mediante LINQ y usar características XML en Visual Basic.

 **Identificador de error:** BC36593

## <a name="to-correct-this-error"></a>Para corregir este error

1. Agregue una `Import` instrucción para el <xref:System.Linq> <xref:System.Data.Linq> espacio de nombres, o <xref:System.Xml.Linq> al archivo de código. También puede importar espacios de nombres para el proyecto mediante la página **referencias** del diseñador de proyectos (**mi proyecto**).

2. Asegúrese de que el tipo que ha identificado como el origen de la consulta es un tipo consultable. Es decir, un tipo que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> .

## <a name="see-also"></a>Vea también

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../programming-guide/language-features/linq/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
- [Referencias y la instrucción Imports](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [Instrucción Imports (Tipo y espacio de nombres de .NET)](../statements/imports-statement-net-namespace-and-type.md)
- [Página Referencias, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
