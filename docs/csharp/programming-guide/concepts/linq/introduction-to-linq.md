---
title: Introducción a LINQ (C#)
ms.date: 07/20/2015
ms.assetid: 54874feb-55e5-4ca8-a9d6-1c1127fd7fb1
ms.openlocfilehash: b8a577c7f1cb89df5534ae0eca893f4db434301e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64596569"
---
# <a name="introduction-to-linq-c"></a>Introducción a LINQ (C#)
Language-Integrated Query (LINQ) es una innovación que se ha presentado en la versión 3.5 de .NET Framework que reduce la distancia entre el mundo de los objetos y el de los datos.  
  
 Tradicionalmente, las consultas con datos se expresaban como cadenas simples sin comprobación de tipos en tiempo de compilación ni compatibilidad con IntelliSense. Además, tendrá que aprender un lenguaje de consulta diferente para cada tipo de origen de datos: bases de datos SQL, documentos XML, varios servicios web y así sucesivamente. LINQ hace que una *consulta* sea una construcción de lenguaje de primera clase en C#. Escribe consultas en colecciones de objetos fuertemente tipadas con palabras clave del lenguaje y operadores familiares.  
  
 Puede escribir consultas LINQ en C# para bases de datos de SQL Server, documentos XML, conjuntos de datos ADO.NET y cualquier colección de objetos que admita <xref:System.Collections.IEnumerable> o la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>. La compatibilidad con LINQ también se proporciona por terceros para muchos servicios web y otras implementaciones de base de datos.  
  
 Puede usar consultas LINQ en proyectos nuevos, o junto con otras consultas que no son de LINQ en proyectos existentes. El único requisito es que el proyecto tenga como destino .NET Framework 3.5 o versiones posteriores.  
  
 En la siguiente ilustración de Visual Studio se muestra una consulta LINQ parcialmente completa en una base de datos de SQL Server en C# y Visual Basic con la comprobación de tipos completa y la compatibilidad con IntelliSense:  
  
 ![Diagrama en el que se muestra una consulta LINQ con IntelliSense.](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a>Pasos siguientes  
 Para obtener más información sobre LINQ, empiece a familiarizarse con algunos conceptos básicos en la sección Introducción de [Introducción a LINQ en C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) y, después, lea la documentación de la tecnología de LINQ en la que esté interesado:  
  
- Bases de datos de SQL Server: [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
  
- Documentos XML: [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)  
  
- Conjuntos de datos de ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
- Colecciones .NET, archivos y cadenas, entre otros: [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a>Vea también

- [Language Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
