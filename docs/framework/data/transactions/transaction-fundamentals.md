---
title: Principios de la transacción
ms.date: 03/30/2017
ms.assetid: 353f4ee2-e6bf-4b1c-b1c8-385fc8a486c0
ms.openlocfilehash: 2df782a40c74c69981e7c25300acdf18f9de3cde
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205861"
---
# <a name="transaction-fundamentals"></a>Principios de la transacción
Las transacciones enlazan varias tareas. Por ejemplo, imagine que una aplicación realiza dos tareas. Primero, crea una nueva tabla en una base de datos. Luego, llama un objeto especializado para recoger, dar formato e insertar los datos en la nueva tabla. Estas dos tareas están relacionadas e incluso son interdependientes, de tal manera que se desea evitar crear una nueva tabla a menos que pueda llenarse de datos. La ejecución de ambas tareas dentro del ámbito de una única transacción refuerzan la conexión entre ellas. En caso de error en la segunda tarea, la primera vuelve al punto anterior a la creación de la nueva tabla.  
  
 Para asegurarse el comportamiento predecible, todas las transacciones deben poseer las propiedades ACID básicas (atómico, coherente, aislado y duradero). Estas propiedades refuerzan el rol de transacciones críticas para una misión como proposiciones todos-o-ninguno. Para obtener más información sobre ACID, consulte [propiedades ACID](https://go.microsoft.com/fwlink/?LinkId=98791). En resumen, ACID garantiza que un conjunto de tareas relacionadas tenga éxito o que produzca un error como una unidad. En la terminología del procesamiento de transacciones, la transacción interrumpe o confirma el procesamiento. Todos los participantes deben garantizar para que se confirme una transacción que cualquier cambio a los datos será permanente. Los cambios deben conservarse a pesar de bloqueos del sistema u otros eventos imprevistos. Tan solo produciéndose un error en uno de los participantes al realizar la garantía, la transacción entera genera un error. Todos los cambios de los datos dentro del ámbito de la transacción se deshacen hasta un punto fijo concreto.  
  
 Una transacción se puede confinar a un recurso de dato único, como una base de datos o una cola de mensajes. El Administrador de la Transacción proporcionado por <xref:System.Transactions>, que genera la ganancia de rendimiento administra la transacción local en este escenario. Controladas por el recurso de datos, estas transacciones son eficaces y fáciles administrar.  
  
 Las transacciones también pueden abarcar varios recursos de los datos. Las transacciones distribuidas le dan la capacidad para incorporar varias operaciones distintas que se producen en sistemas diferentes en un paso único o producir un error en la acción. El coordinador de transacciones distribuidas de Microsoft (MSDTC) que reside en cada sistema coordina las transacciones en este escenario.  
  
 Al desarrollar una aplicación transaccional utilizando las clases proporcionadas por <xref:System.Transactions>, no necesita preocuparse por qué tipo de transacciones necesita o el administrador de transacciones implicado. La infraestructura <xref:System.Transactions> administra automáticamente éstos para usted.  
  
 Cuando crea una transacción, puede especificar el nivel de aislamiento que se aplica a la transacción. El nivel de aislamiento, definido por <xref:System.Transactions.IsolationLevel> la enumeración, determina el nivel de acceso que otras transacciones tendrán a los datos afectados por la transacción.  
  
 Puede crear transacciones mediante ADO.net, <xref:System.EnterpriseServices>o el modelo de programación transaccional proporcionado por el espacio de <xref:System.Transactions> nombres. El tema [características proporcionadas por System.](features-provided-by-system-transactions.md) Transactions describe las características que puede usar para escribir una aplicación transaccional mediante el espacio <xref:System.Transactions> de nombres.  
  
## <a name="see-also"></a>Vea también

- [Características proporcionadas por System.Transactions](features-provided-by-system-transactions.md)
