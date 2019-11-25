---
title: Introducción a LINQ
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: add442583bd81665533b704c0c9721b111cddd78
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74338903"
---
# <a name="introduction-to-linq-visual-basic"></a>Introduction to LINQ (Visual Basic)
Language-Integrated Query (LINQ) es una innovación que se ha presentado en la versión 3.5 de .NET Framework que reduce la distancia entre el mundo de los objetos y el de los datos.  
  
 Tradicionalmente, las consultas con datos se expresaban como cadenas simples sin comprobación de tipos en tiempo de compilación ni compatibilidad con IntelliSense. Además, tiene que aprender un lenguaje de consultas diferente para cada tipo de origen de datos: bases de datos SQL, documentos XML y varios servicios web, entre otros. LINQ makes a *query* a first-class language construct in Visual Basic. Escribe consultas en colecciones de objetos fuertemente tipadas con palabras clave del lenguaje y operadores familiares.  
  
 You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface. La compatibilidad con LINQ también se proporciona por terceros para muchos servicios web y otras implementaciones de base de datos.  
  
 Puede usar consultas LINQ en proyectos nuevos, o junto con otras consultas que no son de LINQ en proyectos existentes. El único requisito es que el proyecto tenga como destino .NET Framework 3.5 o versiones posteriores.  
  
 En la siguiente ilustración de Visual Studio se muestra una consulta LINQ parcialmente completa en una base de datos de SQL Server en C# y Visual Basic con la comprobación de tipos completa y la compatibilidad con IntelliSense.  
  
 ![Diagrama en el que se muestra una consulta LINQ con IntelliSense.](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a>Pasos siguientes  
 To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:  
  
- Bases de datos de SQL Server: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
  
- XML documents: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
- Conjuntos de datos ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
- .NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a>Vea también

- [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
