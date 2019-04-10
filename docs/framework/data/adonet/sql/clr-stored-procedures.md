---
title: Procedimientos almacenados de CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: 9b31d93c1ebc0af9aa8e41b3a4c328af62da7e23
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230816"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="8d646-102">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="8d646-102">CLR Stored Procedures</span></span>
<span data-ttu-id="8d646-103">Los procedimientos almacenados son rutinas que no se pueden utilizar en expresiones escalares.</span><span class="sxs-lookup"><span data-stu-id="8d646-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="8d646-104">Pueden devolver resultados en tabla y mensajes al cliente, invocar instrucciones de lenguaje de definición de datos (DDL) y lenguaje de manipulación de datos (DML) y devolver parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="8d646-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d646-105">Microsoft Visual Basic no admite parámetros de salida de la misma forma que Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="8d646-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="8d646-106">Debe especificar para pasar el parámetro por referencia y aplicar la \<Out() > atributo para representar un parámetro de salida, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8d646-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="8d646-107">Para obtener más información, consulte la versión de [documentación de SQL Server](/sql) para la versión de SQL Server que está usando.</span><span class="sxs-lookup"><span data-stu-id="8d646-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 **<span data-ttu-id="8d646-108">Documentación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="8d646-108">SQL Server documentation</span></span>**

1. [<span data-ttu-id="8d646-109">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="8d646-109">CLR Stored Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="8d646-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d646-110">See also</span></span>

- [<span data-ttu-id="8d646-111">Crear objetos de SQL Server 2005 en código administrado</span><span class="sxs-lookup"><span data-stu-id="8d646-111">Creating SQL Server 2005 Objects In Managed Code</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [<span data-ttu-id="8d646-112">Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="8d646-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
