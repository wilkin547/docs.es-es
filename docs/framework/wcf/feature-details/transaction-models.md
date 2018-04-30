---
title: Modelos de transacción
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c68a23e9ee86050a9db4c63c8c97d017794bce8
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="transaction-models"></a>Modelos de transacción
En este tema se describe la relación entre los modelos de programación de la transacción y los componentes de infraestructura que Microsoft proporciona.  
  
 Al utilizar las transacciones en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], es importante entender que no está seleccionando entre modelos transaccionales diferentes, sino operando en diferentes capas de un modelo integrado y coherente.  
  
 Las secciones siguientes describen los tres componentes de transacción primarios.  
  
## <a name="windows-communication-foundation-transactions"></a>Transacciones de Windows Communication Foundation  
 La compatibilidad con transacciones en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] le permite escribir servicios transaccionales. Además, con su compatibilidad para el protocolo WS-AtomicTransaction (WS-AT), las aplicaciones pueden hacer fluir transacciones a los servicios web creados mediante [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] o tecnologías de otros fabricantes.  
  
 En un servicio o aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], las características de transacciones de  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporcionan atributos y configuración para especificar de manera declarativa cómo y cuándo la infraestructura debería crearse, fluir y sincronizar transacciones.  
  
## <a name="systemtransactions-transactions"></a>Información general sobre las transacciones de System.Transactions  
 El espacio de nombres <xref:System.Transactions> proporciona un modelo de programación explícito según la clase <xref:System.Transactions.Transaction>, así como un modelo de programación implícito utilizando la clase <xref:System.Transactions.TransactionScope>, en la que la infraestructura administra automáticamente las transacciones.  
  
 Para obtener más información acerca de cómo crear una aplicación transaccional mediante estos dos modelos, vea [escribir una aplicación transaccional](http://go.microsoft.com/fwlink/?LinkId=94947).  
  
 En un servicio o aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], <xref:System.Transactions> proporciona el modelo de programación para crear las transacciones dentro de una aplicación cliente y para interactuar explícitamente con una transacción, cuando se requiera, dentro de un servicio.  
  
## <a name="msdtc-transactions"></a>Transacciones de MSDTC  
 Microsoft DTC (Coordinador de transacciones distribuidas) (MSDTC) es un administrador de transacciones que proporciona compatibilidad con transacciones distribuidas.  
  
 Para obtener más información, consulte el [referencia del programador de DTC](http://go.microsoft.com/fwlink/?LinkId=94948).  
  
 En un servicio o aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], MSDTC proporciona la infraestructura para la coordinación de transacciones creada dentro de un cliente o servicio.
