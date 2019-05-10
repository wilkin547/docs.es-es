---
title: Extensión de administración de transacción
ms.date: 03/30/2017
ms.assetid: 1e96331e-31b6-4272-bbbd-29ed1e110460
ms.openlocfilehash: 1e40244e1f6b5ffd7b52584a5da121d1203f8376
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630569"
---
# <a name="transaction-management-escalation"></a>Extensión de administración de transacción
Windows hospeda un conjunto de servicios y módulos que juntos constituyen un administrador de transacciones. La subida de administración de transacciones describe el proceso de migración de una transacción desde uno de los componentes del administrador de transacciones a otro.  
  
 <xref:System.Transactions> incluye un componente de administrador de transacciones que coordina una transacción que implica a lo sumo, un recurso duradero único o varios recursos volátiles. Dado que el administrador de transacciones solo utiliza las llamadas de dominio de intraaplicación, produce el máximo rendimiento. Los programadores no necesitan interactuar directamente con el administrador de transacciones. En su lugar, una infraestructura común que define las interfaces, un comportamiento común, y las clases del asistente <xref:System.Transactions> es proporcionada por el espacio de nombres.  
  
 Cuando desea proporcionar la transacción a un objeto en otro dominio de aplicación (incluso por procesos y límites del equipo) en el mismo equipo, el <xref:System.Transactions> infraestructura realiza una escalada automáticamente la transacción para ser administrados por Microsoft Coordinador de transacciones distribuidas (MSDTC). La subida también se produce si da de alta a otro administrador de recursos duradero. Cuando se realiza una escalada, la transacción sigue siendo administrada en su estado elevado hasta su realización.  
  
 Entre la transacción <xref:System.Transactions> y la transacción de MSDTC, hay un tipo intermediario de transacción disponible a través de la inscripción de fase única promocional (PSPE). PSPE es otro mecanismo importante en <xref:System.Transactions> para la optimización de rendimiento. Permite un recurso duradero remoto, situado en un dominio de aplicación diferente, proceso o equipo, para participar en una transacción <xref:System.Transactions> sin producir que se realice una escalada a una transacción de MSDTC. Para obtener más información sobre PSPE, vea [dar de alta recursos como participantes en una transacción](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md).  
  
## <a name="how-escalation-is-initiated"></a>Cómo se Inicia la subida  
 La subida de la transacción reduce el rendimiento porque MSDTC reside en un proceso independiente, y realizar una escalada de una transacción a MSDTC produce el envío de mensajes durante el proceso. Para mejorar el rendimiento, debería retrasar o evitar la subida a MSDTC; por lo tanto, deberá saber cómo y cuándo se inicia la subida.  
  
 Con tal de que la infraestructura <xref:System.Transactions> administre los recursos volátiles y a lo sumo un recurso duradero que admita notificaciones de la fase única, la transacción permanece en la propiedad de la infraestructura <xref:System.Transactions>. El administrador de transacciones solo es útil a esos recursos que viven en el mismo dominio de aplicación y para los que no se requiere estar registrado (escribir el resultado de la transacción en el disco). Una subida que provoca que la infraestructura <xref:System.Transactions> transfiera la propiedad de la transacción a MSDTC sucede cuando:  
  
- Por lo menos un recurso duradero que no admite notificaciones de la fase única se da de alta en la transacción.  
  
- Por lo menos dos recursos duraderos que admiten notificaciones de la fase del soltero se dan de alta en la transacción. Por ejemplo, dar de alta una conexión única con [!INCLUDE[sqprsqlong](../../../../includes/sqprsqlong-md.md)] no produce  la promoción de ninguna transacción. Sin embargo, cada vez que se abre una segunda conexión a una base de datos [!INCLUDE[sqprsqlong](../../../../includes/sqprsqlong-md.md)] que hace que la base de datos se inscriba, la infraestructura <xref:System.Transactions> detecta que es el segundo recurso duradero en la transacción, y realiza una escalada a una transacción de MSDTC.  
  
- Se invoca una solicitud para "calcular las referencias" de la transacción a un dominio de aplicación diferente o un proceso diferente. Por ejemplo, la serialización del objeto de transacción a través de un límite del dominio de aplicación. Se calculan referencias al objeto de transacción por valor, lo que significa que cualquier intento de pasarlo por un límite de dominio de aplicación (incluso en el mismo proceso) da como resultado la serialización del objeto de transacción. Puede pasar los objetos de transacción realizando una llamada en un método remoto que toma <xref:System.Transactions.Transaction> como un parámetro o puede intentar tener acceso a un componente transaccional-reparado remoto. Esto serializa el objeto de transacción y resulta en una subida, como cuando una transacción se serializa por un dominio de aplicación. Se distribuye y el administrador de transacciones local ya no es adecuado.  
  
 La tabla siguiente hace una lista de todas las posibles excepciones que se pueden producir durante la subida.  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|Intento para realizar una escalada de una transacción con nivel de aislamiento igual a <xref:System.Transactions.IsolationLevel.Snapshot>.|  
|<xref:System.Transactions.TransactionAbortedException>|El administrador de transacciones está inactivo.|  
|<xref:System.Transactions.TransactionException>|Error en la subida, se anula la aplicación.|
