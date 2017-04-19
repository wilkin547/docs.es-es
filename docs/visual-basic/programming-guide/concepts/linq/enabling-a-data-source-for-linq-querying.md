---
title: "Habilitación de un origen de datos para LINQ Querying2 | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c412f0cf-ff0e-4993-ab3d-1b49e23f00f8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 34bdc4e056d982799eac35eb2398dd3f23f6f351
ms.lasthandoff: 03/13/2017

---
# <a name="enabling-a-data-source-for-linq-querying"></a>Habilitar un origen de datos para realizar consultas LINQ
Hay varias maneras de extender [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] para permitir cualquier origen de datos se puede consultar en el [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] patrón. El origen de datos podría ser una estructura de datos, un servicio Web, un sistema de archivos o una base de datos, por nombrar algunos. El modelo de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] facilita a los clientes las consultas a un origen de datos para el que las consultas de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] están habilitadas, ya que la sintaxis y el modelo de la consulta no cambian. Las formas en que [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] se puede extender a estos datos de orígenes son las siguientes:  
  
-   Implementación de la <xref:System.Collections.Generic.IEnumerable%601>interfaz en un tipo para habilitar [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] a la consulta de objetos de ese tipo.</xref:System.Collections.Generic.IEnumerable%601>  
  
-   Crear métodos de operador de consulta estándar como <xref:System.Linq.Enumerable.Where%2A>y <xref:System.Linq.Enumerable.Select%2A>que extienden un tipo para habilitar personalizado [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consultas de ese tipo.</xref:System.Linq.Enumerable.Select%2A> </xref:System.Linq.Enumerable.Where%2A>  
  
-   Crear un proveedor para el origen de datos que implementa el <xref:System.Linq.IQueryable%601>interfaz.</xref:System.Linq.IQueryable%601> Un proveedor que implementa esta interfaz recibe consultas de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] en forma de árboles de expresión, que puede ejecutar de una manera personalizada, por ejemplo, remotamente.  
  
-   Crear un proveedor para el origen de datos que aprovecha las ventajas de un miembro de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] tecnología. Este tipo de proveedor permitiría no sólo las consultas, sino también las operaciones de inserción, actualización y eliminación, así como la asignación para tipos definidos por el usuario.  
  
 En este tema se analizan estas opciones.  
  
## <a name="how-to-enable-linq-querying-of-your-data-source"></a>Cómo habilitar las consultas LINQ de un origen de datos  
  
### <a name="in-memory-data"></a>Datos en memoria  
 Hay dos maneras de habilitar [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consultas de datos en memoria. Si los datos son de un tipo que implementa <xref:System.Collections.Generic.IEnumerable%601>, puede consultar los datos mediante [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] a objetos.</xref:System.Collections.Generic.IEnumerable%601> Si tiene sentido habilitar la enumeración de su tipo implementando la <xref:System.Collections.Generic.IEnumerable%601>interfaz, puede definir [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] estándar métodos de operador de ese tipo de consulta o cree [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] métodos de operador de consulta estándar que extiendan el tipo.</xref:System.Collections.Generic.IEnumerable%601> Las implementaciones personalizadas de los operadores de consulta estándar deberían utilizar ejecución diferida para devolver los resultados.  
  
### <a name="remote-data"></a>Datos remotos  
 La mejor opción para habilitar [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consultar el origen de datos remoto consiste en implementar la <xref:System.Linq.IQueryable%601>interfaz.</xref:System.Linq.IQueryable%601> Sin embargo, esto es diferente de extender un proveedor como [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] para un origen de datos. No hay modelos de proveedor para extender existente [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] tecnologías, como [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], a otros tipos de origen de datos están disponibles en [!INCLUDE[vs_orcas_long](../../../../csharp/misc/includes/vs_orcas_long_md.md)].  
  
## <a name="iqueryable-linq-providers"></a>Proveedores LINQ de IQueryable  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]los proveedores que implementan <xref:System.Linq.IQueryable%601>pueden variar ampliamente en su complejidad.</xref:System.Linq.IQueryable%601> En esta sección se analizan los diferentes niveles de complejidad.  
  
 Un proveedor de `IQueryable` menos complejo podría interactuar con un solo método de un servicio Web. Este tipo de proveedor es muy específico, ya que espera información específica en las consultas que administra. Posee un sistema de tipos cerrado, y expone quizá un único tipo de resultado. La mayor parte de la ejecución de la consulta ocurre localmente, por ejemplo, con el <xref:System.Linq.Enumerable>las implementaciones de operadores de consulta estándar.</xref:System.Linq.Enumerable> Un proveedor menos complejo podría examinar sólo una expresión de llamada a método en el árbol de expresión que representa la consulta, y dejaría que la lógica restante de la consulta se procesara en otra parte.  
  
 Un proveedor `IQueryable` de complejidad media podría destinarse a un origen de datos que tuviera un lenguaje de consulta parcialmente expresivo. Si se destina a un servicio Web, podría comunicarse con más de un método del servicio Web y seleccionar el método que va a llamar en función de la pregunta que plantea la consulta. Un proveedor de complejidad media tendría un sistema de tipos más amplio que un proveedor simple, pero todavía sería un sistema de tipos fijo. Por ejemplo, el proveedor podría exponer tipos que tienen relaciones uno a varios y que se pueden recorrer, pero no proporcionaría tecnología de asignación para tipos definidos por el usuario.  
  
 Un proveedor `IQueryable` complejo, como el proveedor de [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], podría traducir consultas completas de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] en un lenguaje de consulta más expresivo, como SQL. Un proveedor complejo es más general que un proveedor menos complejo, porque puede controlar una gran variedad de preguntas en la consulta. También posee un sistema de tipos abierto y, por tanto, debe contener una amplia infraestructura para utilizar tipos definidos por el usuario. El desarrollo de un proveedor complejo requiere un esfuerzo significativo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.IQueryable%601></xref:System.Linq.IQueryable%601>   
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
