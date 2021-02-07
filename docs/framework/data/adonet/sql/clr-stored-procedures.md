---
description: 'Más información sobre: procedimientos almacenados CLR'
title: Procedimientos almacenados de CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: d136d3dcb12be2f87276a410c9fa0e713b7dfd52
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723626"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="54881-103">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="54881-103">CLR Stored Procedures</span></span>

<span data-ttu-id="54881-104">Los procedimientos almacenados son rutinas que no pueden usarse en expresiones escalares.</span><span class="sxs-lookup"><span data-stu-id="54881-104">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="54881-105">Pueden devolver resultados en tabla y mensajes al cliente, invocar instrucciones de lenguaje de definición de datos (DDL) y lenguaje de manipulación de datos (DML) y devolver parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="54881-105">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="54881-106">Microsoft Visual Basic no admite parámetros de salida de la misma forma que Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="54881-106">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="54881-107">Debe especificar para pasar el parámetro por referencia y aplicar el \<Out()> atributo para representar un parámetro de salida, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="54881-107">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="54881-108">Para obtener información más detallada, consulte la versión de [SQL Server documentación](/sql) de la versión de SQL Server que esté usando.</span><span class="sxs-lookup"><span data-stu-id="54881-108">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="54881-109">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="54881-109">**SQL Server documentation**</span></span>

1. <span data-ttu-id="54881-110">[Procedimientos almacenados de CLR](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="54881-110">[CLR Stored Procedures](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54881-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="54881-111">See also</span></span>

- <span data-ttu-id="54881-112">[Crear SQL Server objetos 2005 en código administrado](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="54881-112">[Creating SQL Server 2005 Objects In Managed Code](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span></span>
- [<span data-ttu-id="54881-113">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="54881-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
