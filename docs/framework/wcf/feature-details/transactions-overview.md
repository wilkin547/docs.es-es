---
title: Información general sobre las transacciones de Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF]
- WCF, transactions
- Windows Communication Foundation, transactions
ms.assetid: c7757854-1207-4019-8b31-552578b7d570
ms.openlocfilehash: 42276a9b450b6f0664901747239195ab13f7c44d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223113"
---
# <a name="windows-communication-foundation-transactions-overview"></a>Información general sobre las transacciones de Windows Communication Foundation
Las transacciones proporcionan una manera de agrupar un conjunto de acciones u operaciones en una unidad indivisible única de ejecución. Una transacción es una colección de operaciones con las propiedades siguientes:  
  
-   Atomicidad. Esto garantiza que todas las actualizaciones completadas en una transacción concreta se confirmadas y sean duraderas o que sean anuladas y reviertan a su estado anterior.  
  
-   Coherencia Esto garantiza que los cambios realizados en una transacción representan una transformación desde un estado coherente a otro. Por ejemplo, una transacción que transfiere el dinero de una cuenta corriente a una cuenta de ahorros no cambia la cantidad de dinero en la cuenta bancaria general.  
  
-   Aislamiento. Esto evita que una transacción obedezca a cambios no confirmados que pertenecen a otras transacciones simultáneas. El aislamiento proporciona una abstracción de simultaneidad y garantiza, al mismo tiempo, que una transacción no tenga un impacto inesperado en la ejecución de otra transacción.  
  
-   Duración. Esto significa que una vez confirmado, las actualizaciones de recursos administrados (como un registro de base de datos) serán persistentes frente a errores.  
  
 Windows Communication Foundation (WCF) proporciona un amplio conjunto de características que le permiten crear transacciones distribuidas en la aplicación de servicio Web.  
  
 WCF implementa la compatibilidad con el protocolo WS-AtomicTransaction (WS-AT) que permite a las aplicaciones WCF envíe transacciones a aplicaciones interoperables, como servicios Web interoperables compilados mediante tecnología de otro fabricante. WCF también implementa la compatibilidad con el protocolo de transacciones OLE, que puede usarse en escenarios donde no es necesario en función de interoperabilidad para habilitar el flujo de transacción.  
  
 Puede utilizar un archivo de configuración de la aplicación para configurar los enlaces con el fin de habilitar o deshabilitar el flujo de la transacción, así como establecer el protocolo de transacción deseado en un enlace. Además, puede establecer los tiempos de espera de la transacción en el nivel del servicio utilizando el archivo de configuración. Para obtener más información, consulte [Habilitar flujo de transacción](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).  
  
 Los atributos de transacción en el espacio de nombres <xref:System.ServiceModel> le permiten hacer lo siguiente:  
  
-   Configure los tiempos de espera de la transacción y filtro del nivel de aislamiento mediante el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute>.  
  
-   Habilite la funcionalidad de las transacciones y configure el comportamiento de realización de transacción mediante el atributo <xref:System.ServiceModel.OperationBehaviorAttribute>.  
  
-   Utilice los atributos <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> de un método de contrato para requerir, permitir o denegar el flujo de transacciones.  
  
 Para obtener más información, consulte [atributos de transacción de ServiceModel](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).  
  
## <a name="see-also"></a>Vea también

- [Atributos de transacción de ServiceModel](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)
- [Habilitar el flujo de transacciones](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
