---
title: Procedimientos almacenados de CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: d2fde4fdcd5ab63906256d814256578b9baa9ecd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782499"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="1cab6-102">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="1cab6-102">CLR Stored Procedures</span></span>
<span data-ttu-id="1cab6-103">Los procedimientos almacenados son rutinas que no se pueden utilizar en expresiones escalares.</span><span class="sxs-lookup"><span data-stu-id="1cab6-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="1cab6-104">Pueden devolver resultados en tabla y mensajes al cliente, invocar instrucciones de lenguaje de definición de datos (DDL) y lenguaje de manipulación de datos (DML) y devolver parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="1cab6-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1cab6-105">Microsoft Visual Basic no admite parámetros de salida de la misma forma que Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="1cab6-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="1cab6-106">Debe especificar para pasar el parámetro por referencia y aplicar el \<atributo out () > para representar un parámetro de salida, como en el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1cab6-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="1cab6-107">Para obtener información más detallada, consulte la versión de [SQL Server documentación](/sql) de la versión de SQL Server que esté usando.</span><span class="sxs-lookup"><span data-stu-id="1cab6-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="1cab6-108">**SQL Server documentación**</span><span class="sxs-lookup"><span data-stu-id="1cab6-108">**SQL Server documentation**</span></span>

1. [<span data-ttu-id="1cab6-109">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="1cab6-109">CLR Stored Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="1cab6-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cab6-110">See also</span></span>

- <span data-ttu-id="1cab6-111">[Crear SQL Server objetos 2005 en código administrado](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1cab6-111">[Creating SQL Server 2005 Objects In Managed Code](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span></span>
- [<span data-ttu-id="1cab6-112">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1cab6-112">ADO.NET Overview</span></span>](../ado-net-overview.md)
