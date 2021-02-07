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
# <a name="clr-stored-procedures"></a>Procedimientos almacenados de CLR

Los procedimientos almacenados son rutinas que no pueden usarse en expresiones escalares. Pueden devolver resultados en tabla y mensajes al cliente, invocar instrucciones de lenguaje de definición de datos (DDL) y lenguaje de manipulación de datos (DML) y devolver parámetros de salida.  
  
> [!NOTE]
> Microsoft Visual Basic no admite parámetros de salida de la misma forma que Microsoft Visual C#. Debe especificar para pasar el parámetro por referencia y aplicar el \<Out()> atributo para representar un parámetro de salida, como se muestra a continuación:  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
Para obtener información más detallada, consulte la versión de [SQL Server documentación](/sql) de la versión de SQL Server que esté usando.
  
 **Documentación de SQL Server**

1. [Procedimientos almacenados de CLR](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))  
  
## <a name="see-also"></a>Vea también

- [Crear SQL Server objetos 2005 en código administrado](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [Información general de ADO.NET](../ado-net-overview.md)
