---
description: 'Más información acerca de cómo: llamar a funciones de base de datos personalizadas'
title: Procedimiento para llamar a funciones de base de datos personalizadas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: f33630f68740877ff2d0e7f0fec7202453d96bf7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696794"
---
# <a name="how-to-call-custom-database-functions"></a>Procedimiento para llamar a funciones de base de datos personalizadas

En este tema se describe cómo llamar a las funciones personalizadas definidas en la base de datos desde consultas LINQ to Entities.

Las funciones de base de datos llamadas desde LINQ to Entities se ejecutan en la base de datos. La ejecución de funciones en la base de datos puede mejorar el rendimiento de la aplicación.

El procedimiento siguiente proporciona un esquema general para llamar a una función de base de datos personalizada. El ejemplo que sigue proporciona más detalles sobre los pasos del procedimiento.

## <a name="to-call-custom-functions-that-are-defined-in-the-database"></a>Para llamar a funciones personalizadas definidas en la base de datos

1. Cree una función personalizada en la base de datos.

     Para obtener más información sobre cómo crear funciones personalizadas en SQL Server, vea [CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql).

2. Declare una función en el lenguaje de definición de esquemas de almacenamiento (SSDL) del archivo .edmx. El nombre de la función debe coincidir con el nombre de la función declarada en la base de datos.

     Para obtener más información, vea [elemento function (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).

3. Agregue un método correspondiente a una clase del código de la aplicación y aplique un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> al método. Tenga en cuenta que los parámetros <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> y <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> de dicho atributo son el nombre del espacio de nombres del modelo conceptual y el nombre de la función en el modelo conceptual, respectivamente. La resolución del nombre de la función para LINQ distingue entre mayúsculas y minúsculas.

4. Llame al método en una consulta LINQ to Entities.  

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo llamar a una función de base de datos personalizada desde una consulta LINQ to Entities. En el ejemplo se usa el modelo School. Para obtener información sobre el modelo School, vea [crear la base de datos de ejemplo School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) y [generar el archivo School. edmx](/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).

El código siguiente agrega la función `AvgStudentGrade` a la base de datos de ejemplo School.

> [!NOTE]
> Los pasos para llamar a una función de base de datos personalizada son los mismos, independientemente del servidor de bases de datos. Sin embargo, el código siguiente es específico para crear una función en una base de datos de SQL Server. El código para crear una función personalizada en otros servidores de bases de datos puede variar.

[!code-sql[DP L2E MapToDBFunction#1](~/samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]

## <a name="example"></a>Ejemplo

A continuación, declare una función en el lenguaje de definición de esquemas de almacenamiento (SSDL) del archivo *. edmx* . El código siguiente declara la `AvgStudentGrade` función en SSDL:

[!code-xml[DP L2E MapToDBFunction#2](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]

## <a name="example"></a>Ejemplo

Ahora, cree un método y asígnelo a la función declarada en el SSDL. El método de la clase siguiente se asigna a dicha función usando un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Cuando se llama a este método, se ejecuta la función correspondiente en la base de datos.

[!code-csharp[DP L2E MapToDBFunction#3](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
[!code-vb[DP L2E MapToDBFunction#3](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]

## <a name="example"></a>Ejemplo

Por último, llame al método en una consulta LINQ to Entities. El código siguiente muestra en la consola los apellidos de los alumnos y sus notas medias:

[!code-csharp[DP L2E MapToDBFunction#4](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
[!code-vb[DP L2E MapToDBFunction#4](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]

## <a name="see-also"></a>Vea también

- [.edmx, Información general sobre el archivo](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Consultas en LINQ to Entities](queries-in-linq-to-entities.md)
