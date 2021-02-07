---
description: 'Más información acerca de: modelos de transacción'
title: Modelos de transacción
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 9abccf74ef5b242cfbe63605046e30e397b8eda6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752709"
---
# <a name="transaction-models"></a>Modelos de transacción

En este tema se describe la relación entre los modelos de programación de la transacción y los componentes de infraestructura que Microsoft proporciona.  
  
 Al utilizar transacciones en Windows Communication Foundation (WCF), es importante entender que no está seleccionando entre diferentes modelos transaccionales, sino que funciona en diferentes capas de un modelo integrado y coherente.  
  
 Las secciones siguientes describen los tres componentes de transacción primarios.  
  
## <a name="windows-communication-foundation-transactions"></a>Transacciones de Windows Communication Foundation  

 La compatibilidad con transacciones en WCF permite escribir servicios transaccionales. Además, gracias a la compatibilidad con el protocolo WS-AtomicTransaction (WS-AT), las aplicaciones pueden fluir transacciones a servicios web creados mediante WCF o tecnología de terceros.  
  
 En una aplicación o servicio WCF, las características de transacción WCF proporcionan atributos y configuraciones para especificar mediante declaración cómo y cuándo la infraestructura debe crear, fluir y sincronizar transacciones.  
  
## <a name="systemtransactions-transactions"></a>Información general sobre las transacciones de System.Transactions  

 El espacio de nombres <xref:System.Transactions> proporciona un modelo de programación explícito según la clase <xref:System.Transactions.Transaction>, así como un modelo de programación implícito utilizando la clase <xref:System.Transactions.TransactionScope>, en la que la infraestructura administra automáticamente las transacciones.  
  
 Para obtener más información sobre cómo crear una aplicación transaccional con estos dos modelos, vea [escribir una aplicación transaccional](https://go.microsoft.com/fwlink/?LinkId=94947).  
  
 En una aplicación o servicio WCF, <xref:System.Transactions> proporciona el modelo de programación para crear transacciones en una aplicación cliente y para interactuar explícitamente con una transacción, cuando es necesario, dentro de un servicio.  
  
## <a name="msdtc-transactions"></a>Transacciones de MSDTC  

 Microsoft DTC (Coordinador de transacciones distribuidas) (MSDTC) es un administrador de transacciones que proporciona compatibilidad con transacciones distribuidas.  
  
 Para obtener más información, vea la [Referencia del programador de DTC](/previous-versions/windows/desktop/ms686108(v=vs.85)).  
  
 En una aplicación o servicio WCF, MSDTC proporciona la infraestructura para la coordinación de transacciones creadas dentro de un cliente o servicio.
