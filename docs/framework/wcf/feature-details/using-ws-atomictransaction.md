---
title: Utilización de WS-AtomicTransaction
ms.date: 03/30/2017
helpviewer_keywords:
- WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
ms.openlocfilehash: 71090efbb096bc3b7b3d6bcf40ff496b78ac6252
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600690"
---
# <a name="using-ws-atomictransaction"></a>Utilización de WS-AtomicTransaction
WS-AtomicTransaction (WS-AT) es un protocolo de transacción interoperable. Permite fluir las transacciones distribuidas utilizando los mensajes de servicio web y coordinar de una manera interoperable entre las infraestructuras de transacción heterogéneas. WS-AT utiliza el protocolo de confirmación en dos fases para controlar un resultado atómico entre las aplicaciones distribuidas, administradores de transacciones y administradores de recursos.  
  
 La implementación de WS-AT Windows Communication Foundation (WCF) incluye un servicio de protocolo integrado en el administrador de transacciones de Microsoft Coordinador de transacciones distribuidas (MSDTC). Con WS-AT, las aplicaciones WCF pueden fluir transacciones a otras aplicaciones, incluidos los servicios web interoperables creados con tecnología de terceros.  
  
 Al fluir una transacción entre una aplicación cliente y una aplicación de servidor, el protocolo de transacción utilizado está determinado por el enlace que el servidor expone en el extremo del cliente seleccionado. Algunos enlaces proporcionados por el sistema de WCF establecen de forma predeterminada el `OleTransactions` Protocolo como el formato de propagación de la transacción, mientras que otros tienen como valor predeterminado WS-at. También puede modificar mediante programación la opción de protocolo de transacción dentro de un enlace determinado.  
  
 La opción del protocolo influye en lo siguiente:  
  
- El formato de los encabezados del mensaje utilizado para fluir la transacción desde el cliente al servidor.  
  
- El protocolo de red utilizado para ejecutar el protocolo de confirmación en dos fases entre el administrador de transacciones del cliente y la transacción del servidor para resolver el resultado de la transacción.  
  
 Si el servidor y el cliente se escriben con WCF, no es necesario usar WS-AT. En su lugar, puede utilizar la configuración predeterminada de `NetTcpBinding` con el atributo `TransactionFlow` habilitado, que utilizará en su lugar el protocolo `OleTransactions`. Para obtener más información, vea [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md). De lo contrario, si está fluyendo las transacciones a los servicios web creados con tecnologías de otro fabricante, deberá utilizar WS-AT.  
  
## <a name="see-also"></a>Vea también

- [Configuración de la compatibilidad con WS-Atomic Transaction](configuring-ws-atomic-transaction-support.md)
