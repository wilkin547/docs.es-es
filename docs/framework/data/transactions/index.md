---
title: Procesar transacciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: effdc8e6-accf-41eb-98a5-431603ba218b
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c66e982715d0f7f97e7a4faa92c2de57f3b1471
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="transaction-processing"></a>Procesar transacciones
Al comprar un libro desde una librería en línea, se intercambia dinero (en forma de crédito) por un libro. Si su crédito es bueno, una serie de operaciones relacionadas le aseguran que obtendrá el libro y que la librería obtendrá su dinero. Sin embargo, si se producir un error en una operación única en la serie durante el intercambio, todo el intercambio falla. No obtiene el libro y la librería no obtiene su dinero.  
  
 La tecnología responsable para realizar el intercambio equilibrado y predecible se denomina procesamiento de transacciones. Las transacciones le aseguran que los recursos orientados a datos no están actualizados permanentemente a menos que todas las operaciones dentro de la unidad transaccional se completen correctamente. Combinando un conjunto de operaciones relacionadas en una unidad que o tiene un éxito rotundo  o bien fracasa completamente, puede simplificar la recuperación de errores y realizar su aplicación con más confianza.  
  
 Los sistemas del procesamiento de transacciones están compuestos de hardware del equipo y software que hospedan una aplicación orientada a transacciones que realiza las transacciones rutinarias necesarias para realizar el negocio. Los ejemplos incluyen sistemas que administran entradas del pedido de ventas, reservas de la línea aérea, nómina, registros del empleado, fabricación y envío.  
  
 En esta sección se proporciona tanto información general sobre procesamiento de transacciones como información concreta sobre cómo escribir las aplicaciones transaccionales y los administradores de recursos mediante Microsoft .NET Framework.  
  
## <a name="in-this-section"></a>En esta sección  
 [Principios de la transacción](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 Introduce condiciones del procesamiento de transacciones básicas y conceptos.  
  
 [Características proporcionadas por System.Transactions](../../../../docs/framework/data/transactions/features-provided-by-system-transactions.md)  
 Discute cómo puede utilizar las características en System.Transactions para escribir su propia aplicación transaccional.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Transactions>  
 Proporciona las clases que permiten al código participar en transacciones. Las clases admiten transacciones con varios participantes distribuidos, varias notificaciones de fase e inscripciones duraderas.
