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
# <a name="clr-stored-procedures"></a>Procedimientos almacenados de CLR
Los procedimientos almacenados son rutinas que no se pueden utilizar en expresiones escalares. Pueden devolver resultados en tabla y mensajes al cliente, invocar instrucciones de lenguaje de definición de datos (DDL) y lenguaje de manipulación de datos (DML) y devolver parámetros de salida.  
  
> [!NOTE]
>  Microsoft Visual Basic no admite parámetros de salida de la misma forma que Microsoft Visual C#. Debe especificar para pasar el parámetro por referencia y aplicar la \<Out() > atributo para representar un parámetro de salida, como en el siguiente ejemplo:  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
Para obtener más información, consulte la versión de [documentación de SQL Server](/sql) para la versión de SQL Server que está usando.
  
 **Documentación de SQL Server**

1. [Procedimientos almacenados de CLR](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>Vea también  
 [Crear objetos de SQL Server 2005 en código administrado](https://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
