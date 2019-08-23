---
title: Procedimientos almacenados de CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: c02efa3f0a91d176b626761335bd2d5a2b96b966
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917954"
---
# <a name="clr-stored-procedures"></a>Procedimientos almacenados de CLR
Los procedimientos almacenados son rutinas que no se pueden utilizar en expresiones escalares. Pueden devolver resultados en tabla y mensajes al cliente, invocar instrucciones de lenguaje de definición de datos (DDL) y lenguaje de manipulación de datos (DML) y devolver parámetros de salida.  
  
> [!NOTE]
> Microsoft Visual Basic no admite parámetros de salida de la misma forma que Microsoft Visual C#. Debe especificar para pasar el parámetro por referencia y aplicar el \<atributo out () > para representar un parámetro de salida, como en el siguiente:  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
Para obtener información más detallada, consulte la versión de [SQL Server documentación](/sql) de la versión de SQL Server que esté usando.
  
 **SQL Server documentación**

1. [Procedimientos almacenados de CLR](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>Vea también

- [Crear SQL Server objetos 2005 en código administrado](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
