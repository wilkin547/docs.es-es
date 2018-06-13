---
title: Utilización de WS-AtomicTransaction
ms.date: 03/30/2017
helpviewer_keywords:
- WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
ms.openlocfilehash: 7880d46d4827b36c7806c61877edf79faa766371
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498262"
---
# <a name="using-ws-atomictransaction"></a>Utilización de WS-AtomicTransaction
WS-AtomicTransaction (WS-AT) es un protocolo de transacción interoperable. Permite fluir las transacciones distribuidas utilizando los mensajes de servicio web y coordinar de una manera interoperable entre las infraestructuras de transacción heterogéneas. WS-AT utiliza el protocolo de confirmación en dos fases para controlar un resultado atómico entre las aplicaciones distribuidas, administradores de transacciones y administradores de recursos.  
  
 La implementación de WS-AT Windows Communication Foundation (WCF) proporciona incluye un servicio de protocolo integrado en el Administrador de transacciones del Coordinador de transacciones distribuidas de Microsoft (MSDTC). Con WS-AT, las aplicaciones WCF pueden fluir transacciones a otras aplicaciones, incluidos los servicios Web creados con tecnología de otro fabricante.  
  
 Al fluir una transacción entre una aplicación cliente y una aplicación de servidor, el protocolo de transacción utilizado está determinado por el enlace que el servidor expone en el punto de conexión del cliente seleccionado. Algunos predeterminado de enlaces proporcionados por el sistema WCF para especificar el `OleTransactions` protocolo como el formato de propagación de transacción, mientras que otros usuarios de forma predeterminada la especificación de WS-AT. También puede modificar mediante programación la opción de protocolo de transacción dentro de un enlace determinado.  
  
 La opción del protocolo influye en lo siguiente:  
  
-   El formato de los encabezados del mensaje utilizado para fluir la transacción desde el cliente al servidor.  
  
-   El protocolo de red utilizado para ejecutar el protocolo de confirmación en dos fases entre el administrador de transacciones del cliente y la transacción del servidor para resolver el resultado de la transacción.  
  
 Si el servidor y el cliente se escriben con WCF, no es necesario utilizar WS-AT. En su lugar, puede utilizar la configuración predeterminada de `NetTcpBinding` con el atributo `TransactionFlow` habilitado, que utilizará en su lugar el protocolo `OleTransactions`. Para obtener más información, consulte [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md). De lo contrario, si está fluyendo las transacciones a los servicios web creados con tecnologías de otro fabricante, deberá utilizar WS-AT.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de la compatibilidad con WS-Atomic Transaction](../../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
