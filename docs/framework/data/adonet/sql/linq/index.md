---
title: LINQ to SQL
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 62f7a3b0fcefa9eb6f5b56d96217a9988a193104
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] es un componente de [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] versión 3.5 que proporciona una infraestructura en tiempo de ejecución para administrar los datos relacionales como objetos.  
  
> [!NOTE]
>  Los datos relacionales se muestran como una colección de tablas bidimensionales (*relaciones* o *archivos sin formato*), donde las columnas comunes relacionan las tablas entre sí. Para utilizar [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] con eficacia, debe estar un poco familiarizado con los principios subyacentes de las bases de datos relacionales.  
  
 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], el modelo de datos de una base de datos relacional se asigna a un modelo de objetos expresado en el lenguaje de programación del desarrollador. Cuando la aplicación se ejecuta, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte a SQL las consultas integradas en el lenguaje en el modelo de objetos y las envía a la base de datos para su ejecución. Cuando la base de datos devuelve los resultados, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] los vuelve a convertir en objetos con los que pueda trabajar en su propio lenguaje de programación.  
  
 Los desarrolladores de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] normalmente usan el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], que proporciona una interfaz de usuario para implementar muchas de las características de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 La documentación que se incluye con esta versión de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] describe las unidades de creación básicas, los procesos y las técnicas que necesita para crear aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. También puede buscar Microsoft Docs problemas concretos y participar en la [foro de LINQ](http://go.microsoft.com/fwlink/?LinkId=76488), dónde debatirá detalladamente temas más complejos con expertos. Por último, en las notas del producto [LINQ to SQL: .NET Language-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205) (LINQ to SQL: consultas integradas en el lenguaje .NET para datos relacionales) se explica con detalle la tecnología [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], junto con ejemplos de código de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] y C#.  
  
## <a name="in-this-section"></a>En esta sección  
 [Introducción](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 Proporciona una introducción a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], junto con información sobre cómo empezar a usar [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Guía de programación](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Proporciona pasos para realizar operaciones de asignación, consulta, actualización, depuración, y otras tareas similares.  
  
 [Referencia](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 Proporciona información de referencia sobre distintos aspectos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Entre sus temas, se pueden citar Correspondencia de tipos SQL-CLR o Conversión de operadores de consulta estándar.  
  
 [Ejemplos](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 Proporciona vínculos a ejemplos de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] y C#.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [LINQ (Language Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 Proporciona información general sobre las tecnologías [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 Describe las tecnologías [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] para usuarios de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)].  
  
 [LINQ to ADO.NET](http://msdn.microsoft.com/library/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 Vínculos al portal de [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)].  
  
 [Tutoriales de LINQ to SQL](http://msdn.microsoft.com/library/308e66ac-f704-4e00-9b4e-7af0045a2374)  
 Enumera los tutoriales disponibles para [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 Describe cómo descargar las bases de datos de ejemplo que se usan en la documentación.  
  
 [Información general sobre la tecnología de LinqDataSource](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136)  
 Describe cómo el control <xref:System.Web.UI.WebControls.LinqDataSource> expone [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] para los desarrolladores web a través de la arquitectura de control de código fuente de datos de [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)].
