---
title: Habilitar un origen de datos para realizar consultas LINQ
description: Obtenga información sobre cómo extender LINQ en C# para habilitar la consulta de cualquier origen de datos en el patrón LINQ, lo que facilita a los clientes la consulta de un origen de datos.
ms.date: 07/20/2015
ms.assetid: d2ef04a5-31a6-45cb-af9a-a5ce7732662c
ms.openlocfilehash: 84769e27e3f8b8d7ee30b79c219b180333337af9
ms.sourcegitcommit: 4d5e25a46aa7cd0d29b4b9227b92987354d444c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98794826"
---
# <a name="enabling-a-data-source-for-linq-querying"></a>Habilitar un origen de datos para realizar consultas LINQ

Hay varias maneras de extender LINQ para permitir consultar cualquier origen de datos en el modelo LINQ El origen de datos podría ser una estructura de datos, un servicio Web, un sistema de archivos o una base de datos, por nombrar algunos. El modelo LINQ facilita a los clientes las consultas a un origen de datos para el que las consultas LINQ están habilitadas, ya que la sintaxis y el modelo de consulta no cambian. Las maneras en las que LINQ se puede extender a estos orígenes de datos son las siguientes:  
  
- Implementar la interfaz <xref:System.Collections.Generic.IEnumerable%601> en un tipo para habilitar las consultas de LINQ to Objects para ese tipo.  
  
- Crear métodos de operador de consulta estándar como <xref:System.Linq.Enumerable.Where%2A> y <xref:System.Linq.Enumerable.Select%2A> que extienden un tipo para habilitar las consultas personalizadas LINQ para ese tipo.  
  
- Crear un proveedor para el origen de datos que implementa la interfaz <xref:System.Linq.IQueryable%601>. Un proveedor que implementa esta interfaz recibe consultas LINQ en forma de árboles de expresión, que puede ejecutar de una manera personalizada, por ejemplo, remotamente.  
  
- Crear un proveedor para el origen de datos que aproveche una tecnología de LINQ existente. Este tipo de proveedor permitiría no sólo las consultas, sino también las operaciones de inserción, actualización y eliminación, así como la asignación para tipos definidos por el usuario.  
  
 En este tema se analizan estas opciones.  
  
## <a name="how-to-enable-linq-querying-of-your-data-source"></a>Cómo habilitar las consultas LINQ de un origen de datos  
  
### <a name="in-memory-data"></a>Datos en memoria  

 Hay dos maneras de habilitar las consultas LINQ para datos en memoria. Si los datos son de un tipo que implementa <xref:System.Collections.Generic.IEnumerable%601>, puede consultar los datos utilizando LINQ to Objects. Si no tiene sentido habilitar la enumeración de su tipo implementando la interfaz <xref:System.Collections.Generic.IEnumerable%601>, puede definir métodos de operador de consulta estándar de LINQ en ese tipo o crear métodos de operador de consulta estándar de LINQ que extiendan el tipo. Las implementaciones personalizadas de los operadores de consulta estándar deberían utilizar ejecución diferida para devolver los resultados.  
  
### <a name="remote-data"></a>Datos remotos  

 La mejor opción para permitir las consultas LINQ para un origen de datos remoto consiste en implementar la interfaz <xref:System.Linq.IQueryable%601>. Sin embargo, esto es diferente de extender un proveedor como [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] para un origen de datos.
  
## <a name="iqueryable-linq-providers"></a>Proveedores LINQ de IQueryable  

 Los proveedores de LINQ que implementan <xref:System.Linq.IQueryable%601> pueden variar ampliamente en su complejidad. En esta sección se analizan los diferentes niveles de complejidad.  
  
 Un proveedor de `IQueryable` menos complejo podría interactuar con un solo método de un servicio Web. Este tipo de proveedor es muy específico, ya que espera información específica en las consultas que administra. Posee un sistema de tipos cerrado, y expone quizá un único tipo de resultado. La mayor parte de la ejecución de la consulta ocurre localmente, por ejemplo, utilizando las implementaciones <xref:System.Linq.Enumerable> de los operadores de consulta estándar. Un proveedor menos complejo podría examinar sólo una expresión de llamada a método en el árbol de expresión que representa la consulta, y dejaría que la lógica restante de la consulta se procesara en otra parte.  
  
 Un proveedor `IQueryable` de complejidad media podría destinarse a un origen de datos que tuviera un lenguaje de consulta parcialmente expresivo. Si se destina a un servicio Web, podría comunicarse con más de un método del servicio Web y seleccionar el método que va a llamar en función de la pregunta que plantea la consulta. Un proveedor de complejidad media tendría un sistema de tipos más amplio que un proveedor simple, pero todavía sería un sistema de tipos fijo. Por ejemplo, el proveedor podría exponer tipos que tienen relaciones uno a varios y que se pueden recorrer, pero no proporcionaría tecnología de asignación para tipos definidos por el usuario.  
  
 Un proveedor `IQueryable` complejo, como el proveedor de [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], podría traducir consultas completas LINQ en un lenguaje de consulta más expresivo, como SQL. Un proveedor complejo es más general que un proveedor menos complejo, porque puede controlar una gran variedad de preguntas en la consulta. También posee un sistema de tipos abierto y, por tanto, debe contener una amplia infraestructura para utilizar tipos definidos por el usuario. El desarrollo de un proveedor complejo requiere un esfuerzo significativo.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Linq.IQueryable%601>
- <xref:System.Collections.Generic.IEnumerable%601>
- <xref:System.Linq.Enumerable>
- [Información general sobre operadores de consulta estándar (C#)](./standard-query-operators-overview.md)
- [LINQ to Objects (C#)](./linq-to-objects.md)
