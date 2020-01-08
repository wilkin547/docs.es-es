---
title: LINQ to ADO.NET (Página de portal)
ms.date: 07/20/2015
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
ms.openlocfilehash: d5d7ba8230ae9737d4938c1c8c55f7cd4330b117
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636502"
---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (Página de portal)
LINQ to ADO.NET le permite consultar cualquier objeto enumerable en ADO.NET mediante el modelo de programación Language-Integrated Query (LINQ).  
  
> [!NOTE]
> La documentación LINQ to ADO.NET se encuentra en la sección ADO.NET del SDK de .NET Framework: [LINQ y ADO.net](../../../../framework/data/adonet/linq-and-ado-net.md).
  
 Hay tres tecnologías de ADO.NET Language Integrated Query (LINQ) independientes: LINQ to DataSet, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]y LINQ to Entities. LINQ to DataSet proporciona consultas más ricas y optimizadas de <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] permite consultar directamente los esquemas de base de datos de SQL Server y LINQ to Entities permite consultar un modelo Entity Data Model.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> es uno de los componentes más usados de ADO.NET, además de un elemento clave del modelo de programación desconectado en el que se basa ADO.NET. En cambio, a pesar de su importancia, <xref:System.Data.DataSet> tiene funciones de consulta limitadas.  
  
 LINQ to DataSet permite compilar capacidades de consulta más complejas en <xref:System.Data.DataSet> mediante la misma funcionalidad de consulta disponible para muchos otros orígenes de datos.  
  
 Para más información, vea [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] proporciona una infraestructura en tiempo de ejecución para administrar los datos relacionales como objetos. En [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], el modelo de datos de una base de datos relacional se asigna a un modelo de objetos expresado en el lenguaje de programación del desarrollador. Cuando se ejecuta la aplicación, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] convierte a SQL las consultas integradas en el lenguaje en el modelo de objetos y las envía a la base de datos para su ejecución. Cuando la base de datos devuelve los resultados, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] los vuelve a convertir en objetos que se pueden manipular.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] incluye compatibilidad con los procedimientos almacenados y las funciones definidas por el usuario de la base de datos, además de con la herencia en el modelo de objetos.  
  
 Para más información, vea [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 A través del modelo Entity Data Model, los datos relacionales se exponen como objetos en el entorno .NET. Esto hace que la capa de objetos sea un objetivo ideal para la compatibilidad con LINQ, lo que permite a los desarrolladores formular consultas en la base de datos desde el lenguaje usado para compilar la lógica de negocios. Esta funcionalidad se conoce como LINQ to Entities. Para más información, vea [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Vea también

- [LINQ y ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)
- [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
