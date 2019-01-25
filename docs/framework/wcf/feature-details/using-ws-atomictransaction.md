---
title: Utilización de WS-AtomicTransaction
ms.date: 03/30/2017
helpviewer_keywords:
- WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
ms.openlocfilehash: a06d441ad1a48b0ddc8631c362d14a52ae882c3b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584875"
---
# <a name="using-ws-atomictransaction"></a>Utilización de WS-AtomicTransaction
WS-AtomicTransaction (WS-AT) es un protocolo de transacción interoperable. Permite fluir las transacciones distribuidas utilizando los mensajes de servicio web y coordinar de una manera interoperable entre las infraestructuras de transacción heterogéneas. WS-AT utiliza el protocolo de confirmación en dos fases para controlar un resultado atómico entre las aplicaciones distribuidas, administradores de transacciones y administradores de recursos.  
  
 Windows Communication Foundation (WCF) proporciona la implementación de WS-AT incluye un servicio de protocolo integrado en el Administrador de transacciones del Coordinador de transacciones distribuidas de Microsoft (MSDTC). Usar WS-AT, las aplicaciones WCF pueden fluir transacciones a otras aplicaciones, incluidos los servicios Web creados con tecnología de otro fabricante.  
  
 Al fluir una transacción entre una aplicación cliente y una aplicación de servidor, el protocolo de transacción utilizado está determinado por el enlace que el servidor expone en el punto de conexión del cliente seleccionado. Algún valor predeterminado enlaces proporcionados por el sistema WCF para especificar el `OleTransactions` protocolo como el formato de propagación de transacción, mientras que otros usuarios de forma predeterminada especificando WS-AT. También puede modificar mediante programación la opción de protocolo de transacción dentro de un enlace determinado.  
  
 La opción del protocolo influye en lo siguiente:  
  
-   El formato de los encabezados del mensaje utilizado para fluir la transacción desde el cliente al servidor.  
  
-   El protocolo de red utilizado para ejecutar el protocolo de confirmación en dos fases entre el administrador de transacciones del cliente y la transacción del servidor para resolver el resultado de la transacción.  
  
 Si el servidor y cliente se escriben con WCF, no es necesario usar WS-AT. En su lugar, puede utilizar la configuración predeterminada de `NetTcpBinding` con el atributo `TransactionFlow` habilitado, que utilizará en su lugar el protocolo `OleTransactions`. Para obtener más información, consulte [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md). De lo contrario, si está fluyendo las transacciones a los servicios web creados con tecnologías de otro fabricante, deberá utilizar WS-AT.  
  
## <a name="see-also"></a>Vea también
- [Configuración de la compatibilidad con WS-Atomic Transaction](../../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
