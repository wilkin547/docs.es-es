---
title: LINQ to SQL
description: LINQ to SQL es un componente de la .NET Framework que proporciona una infraestructura en tiempo de ejecución para administrar los datos relacionales como objetos.
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: 13502bfee3ee24764d190dace1512bc958343973
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286318"
---
# <a name="linq-to-sql"></a>LINQ a SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]es un componente de .NET Framework versión 3,5 que proporciona una infraestructura en tiempo de ejecución para administrar datos relacionales como objetos.  
  
> [!NOTE]
> Los datos relacionales se muestran como una colección de tablas bidimensionales (*relaciones* o *archivos sin formato*), donde las columnas comunes relacionan las tablas entre sí. Para utilizar [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] con eficacia, debe estar un poco familiarizado con los principios subyacentes de las bases de datos relacionales.  
  
 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], el modelo de datos de una base de datos relacional se asigna a un modelo de objetos expresado en el lenguaje de programación del desarrollador. Cuando la aplicación se ejecuta, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte a SQL las consultas integradas en el lenguaje en el modelo de objetos y las envía a la base de datos para su ejecución. Cuando la base de datos devuelve los resultados, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] los vuelve a convertir en objetos con los que pueda trabajar en su propio lenguaje de programación.  
  
 Los desarrolladores que usan Visual Studio suelen usar el Object Relational Designer, que proporciona una interfaz de usuario para implementar muchas de las características de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .  
  
 La documentación que se incluye con esta versión de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] describe las unidades de creación básicas, los procesos y las técnicas que necesita para crear aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. También puede buscar en Microsoft Docs para ver si hay problemas específicos y puede participar en el [Foro de LINQ](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), donde puede discutir con mayor detalle temas más complejos con expertos. Por último, el [LINQ to SQL: Language-Integrated Query para datos relacionales tecnología de detalles de](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) las notas del producto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , completos con Visual Basic y ejemplos de código de C#.  
  
## <a name="in-this-section"></a>En esta sección  
 [Introducción](getting-started.md)  
 Proporciona una introducción a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], junto con información sobre cómo empezar a usar [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Guía de programación](programming-guide.md)  
 Proporciona pasos para realizar operaciones de asignación, consulta, actualización, depuración, y otras tareas similares.  
  
 [Referencia](reference.md)  
 Proporciona información de referencia sobre distintos aspectos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Entre sus temas, se pueden citar Correspondencia de tipos SQL-CLR o Conversión de operadores de consulta estándar.  
  
 [Muestras](samples.md)  
 Proporciona vínculos a ejemplos de Visual Basic y C#.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Language-Integrated Query (LINQ)-C #](../../../../../csharp/programming-guide/concepts/linq/index.md)\
 Proporciona información general sobre las tecnologías LINQ en C#.

 [Language Integrated Query (LINQ) (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Proporciona información general sobre las tecnologías LINQ en Visual Basic.
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 Describe las tecnologías LINQ para Visual Basic usuarios.  
  
 [LINQ y ADO.NET](../../linq-and-ado-net.md)  
 Vínculos al portal de ADO.NET.  
  
 [Tutoriales de LINQ to SQL](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))  
 Enumera los tutoriales disponibles para [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Descargar bases de datos de ejemplo](downloading-sample-databases.md)  
 Describe cómo descargar las bases de datos de ejemplo que se usan en la documentación.  
  
 [Información general sobre el control de servidor Web LinqDataSource](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))  
 Describe cómo el <xref:System.Web.UI.WebControls.LinqDataSource> control expone Language-Integrated Query (LINQ) a los desarrolladores web a través de la arquitectura de control de código fuente de datos de ASP.net.
