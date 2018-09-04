---
title: Procedimientos almacenados de CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: 1f8aa6fb9243706d07caa4527af0c4c880aa70a6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503116"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="5b5c5-102">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="5b5c5-102">CLR Stored Procedures</span></span>
<span data-ttu-id="5b5c5-103">Los procedimientos almacenados son rutinas que no se pueden utilizar en expresiones escalares.</span><span class="sxs-lookup"><span data-stu-id="5b5c5-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="5b5c5-104">Pueden devolver resultados en tabla y mensajes al cliente, invocar instrucciones de lenguaje de definición de datos (DDL) y lenguaje de manipulación de datos (DML) y devolver parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="5b5c5-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b5c5-105">Microsoft Visual Basic no admite parámetros de salida de la misma forma que Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="5b5c5-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="5b5c5-106">Debe especificar para pasar el parámetro por referencia y aplicar la \<Out() > atributo para representar un parámetro de salida, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5b5c5-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="5b5c5-107">Para obtener más información, consulte la versión de [documentación de SQL Server](/sql) para la versión de SQL Server que está usando.</span><span class="sxs-lookup"><span data-stu-id="5b5c5-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="5b5c5-108">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="5b5c5-108">**SQL Server documentation**</span></span>

1. [<span data-ttu-id="5b5c5-109">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="5b5c5-109">CLR Stored Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="5b5c5-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b5c5-110">See Also</span></span>  
 [<span data-ttu-id="5b5c5-111">Crear objetos de SQL Server 2005 en código administrado</span><span class="sxs-lookup"><span data-stu-id="5b5c5-111">Creating SQL Server 2005 Objects In Managed Code</span></span>](https://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="5b5c5-112">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="5b5c5-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
