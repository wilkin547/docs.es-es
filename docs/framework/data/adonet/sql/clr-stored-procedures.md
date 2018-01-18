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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: aebc681482482c364f762b12065cf041f4976be9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="clr-stored-procedures"></a>Procedimientos almacenados de CLR
Los procedimientos almacenados son rutinas que no se pueden utilizar en expresiones escalares. Pueden devolver resultados en tabla y mensajes al cliente, invocar instrucciones de lenguaje de definición de datos (DDL) y lenguaje de manipulación de datos (DML) y devolver parámetros de salida.  
  
> [!NOTE]
>  Microsoft Visual Basic no admite parámetros de salida de la misma forma que Microsoft Visual C#. Debe especificar para pasar el parámetro por referencia y aplicar la \<Out() > atributo para representar un parámetro de salida, como en el siguiente ejemplo:  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.  
  
 **Libros en pantalla de SQL Server**  
  
1.  [Procedimientos almacenados de CLR](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>Vea también  
 [Crear objetos de SQL Server 2005 en código administrado](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
