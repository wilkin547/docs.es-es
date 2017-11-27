---
title: Procedimientos almacenados de CLR
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1e55222c16d223a86e1e11ce2b985ec0f4d8eaa3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="b81f6-102">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="b81f6-102">CLR Stored Procedures</span></span>
<span data-ttu-id="b81f6-103">Los procedimientos almacenados son rutinas que no se pueden utilizar en expresiones escalares.</span><span class="sxs-lookup"><span data-stu-id="b81f6-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="b81f6-104">Pueden devolver resultados en tabla y mensajes al cliente, invocar instrucciones de lenguaje de definición de datos (DDL) y lenguaje de manipulación de datos (DML) y devolver parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="b81f6-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b81f6-105">Microsoft Visual Basic no admite parámetros de salida de la misma forma que Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="b81f6-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="b81f6-106">Debe especificar para pasar el parámetro por referencia y aplicar la \<Out() > atributo para representar un parámetro de salida, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b81f6-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 <span data-ttu-id="b81f6-107">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b81f6-107">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="b81f6-108">**Libros en pantalla de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b81f6-108">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="b81f6-109">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="b81f6-109">CLR Stored Procedures</span></span>](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="b81f6-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b81f6-110">See Also</span></span>  
 [<span data-ttu-id="b81f6-111">Crear objetos de SQL Server 2005 en código administrado</span><span class="sxs-lookup"><span data-stu-id="b81f6-111">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="b81f6-112">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="b81f6-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
