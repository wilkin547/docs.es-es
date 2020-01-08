---
title: Habilitar un origen de datos para LINQ Querying2
ms.date: 07/20/2015
ms.assetid: c412f0cf-ff0e-4993-ab3d-1b49e23f00f8
ms.openlocfilehash: ecd43b371a8e907e9bcfc8687c04bdd0350235ac
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636892"
---
# <a name="enabling-a-data-source-for-linq-querying"></a>Habilitar un origen de datos para realizar consultas LINQ

Hay varias maneras de ampliar LINQ para habilitar la consulta de cualquier origen de datos en el modelo LINQ. El origen de datos podría ser una estructura de datos, un servicio Web, un sistema de archivos o una base de datos, por nombrar algunos. El modelo LINQ facilita a los clientes la consulta de un origen de datos para el que está habilitada la consulta LINQ, ya que la sintaxis y el patrón de la consulta no cambian. Las formas en que LINQ se puede extender a estos orígenes de datos son las siguientes:

- Implementar la interfaz de <xref:System.Collections.Generic.IEnumerable%601> en un tipo para habilitar LINQ to Objects consulta de ese tipo.

- Crear métodos de operador de consulta estándar como <xref:System.Linq.Enumerable.Where%2A> y <xref:System.Linq.Enumerable.Select%2A> que extienden un tipo para habilitar las consultas LINQ personalizadas de ese tipo.

- Crear un proveedor para el origen de datos que implementa la interfaz <xref:System.Linq.IQueryable%601>. Un proveedor que implementa esta interfaz recibe consultas LINQ en forma de árboles de expresión, que puede ejecutar de una manera personalizada, por ejemplo de forma remota.

- Crear un proveedor para el origen de datos que aprovecha una tecnología de LINQ existente. Este tipo de proveedor permitiría no sólo las consultas, sino también las operaciones de inserción, actualización y eliminación, así como la asignación para tipos definidos por el usuario.

En este tema se analizan estas opciones.

## <a name="how-to-enable-linq-querying-of-your-data-source"></a>Cómo habilitar las consultas LINQ de un origen de datos

### <a name="in-memory-data"></a>Datos en memoria
 Hay dos maneras de habilitar las consultas LINQ de datos en memoria. Si los datos son de un tipo que implementa <xref:System.Collections.Generic.IEnumerable%601>, puede consultar los datos mediante LINQ to Objects. Si no tiene sentido habilitar la enumeración de su tipo implementando la interfaz <xref:System.Collections.Generic.IEnumerable%601>, puede definir métodos de operador de consulta estándar de LINQ en ese tipo o crear métodos de operador de consulta estándar de LINQ que extiendan el tipo. Las implementaciones personalizadas de los operadores de consulta estándar deberían utilizar ejecución diferida para devolver los resultados.

### <a name="remote-data"></a>Datos remotos
 La mejor opción para habilitar las consultas LINQ de un origen de datos remoto consiste en implementar la interfaz de <xref:System.Linq.IQueryable%601>. Sin embargo, esto es diferente de extender un proveedor como [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] para un origen de datos. En Visual Studio 2008, no se dispone de modelos de proveedor para extender las tecnologías de LINQ existentes, como [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], a otros tipos de origen de datos.

## <a name="iqueryable-linq-providers"></a>Proveedores LINQ de IQueryable
 Los proveedores LINQ que implementan <xref:System.Linq.IQueryable%601> pueden variar ampliamente en su complejidad. En esta sección se analizan los diferentes niveles de complejidad.

 Un proveedor de `IQueryable` menos complejo podría interactuar con un solo método de un servicio Web. Este tipo de proveedor es muy específico, ya que espera información específica en las consultas que administra. Posee un sistema de tipos cerrado, y expone quizá un único tipo de resultado. La mayor parte de la ejecución de la consulta ocurre localmente, por ejemplo, utilizando las implementaciones <xref:System.Linq.Enumerable> de los operadores de consulta estándar. Un proveedor menos complejo podría examinar sólo una expresión de llamada a método en el árbol de expresión que representa la consulta, y dejaría que la lógica restante de la consulta se procesara en otra parte.

 Un proveedor `IQueryable` de complejidad media podría destinarse a un origen de datos que tuviera un lenguaje de consulta parcialmente expresivo. Si se destina a un servicio Web, podría comunicarse con más de un método del servicio Web y seleccionar el método que va a llamar en función de la pregunta que plantea la consulta. Un proveedor de complejidad media tendría un sistema de tipos más amplio que un proveedor simple, pero todavía sería un sistema de tipos fijo. Por ejemplo, el proveedor podría exponer tipos que tienen relaciones uno a varios y que se pueden recorrer, pero no proporcionaría tecnología de asignación para tipos definidos por el usuario.

 Un proveedor de `IQueryable` complejo, como el proveedor de [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], puede traducir las consultas LINQ completas a un lenguaje de consulta expresivo, como SQL. Un proveedor complejo es más general que un proveedor menos complejo, porque puede controlar una gran variedad de preguntas en la consulta. También posee un sistema de tipos abierto y, por tanto, debe contener una amplia infraestructura para utilizar tipos definidos por el usuario. El desarrollo de un proveedor complejo requiere un esfuerzo significativo.

## <a name="see-also"></a>Vea también

- <xref:System.Linq.IQueryable%601>
- <xref:System.Collections.Generic.IEnumerable%601>
- <xref:System.Linq.Enumerable>
- [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
