---
title: Modelos de transacción
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 8731b72d0657aa420dbb020e216c3af059916ce9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43474231"
---
# <a name="transaction-models"></a>Modelos de transacción
En este tema se describe la relación entre los modelos de programación de la transacción y los componentes de infraestructura que Microsoft proporciona.  
  
 Cuando se usan transacciones en Windows Communication Foundation (WCF), es importante entender que no está seleccionando entre modelos transaccionales diferentes pero operando en diferentes niveles de un modelo integrado y coherente.  
  
 Las secciones siguientes describen los tres componentes de transacción primarios.  
  
## <a name="windows-communication-foundation-transactions"></a>Transacciones de Windows Communication Foundation  
 La compatibilidad con transacciones en WCF permite que escribir servicios transaccionales. Además, con su compatibilidad con el protocolo WS-AtomicTransaction (WS-AT), las aplicaciones pueden fluir transacciones a servicios Web creados mediante WCF o tecnología de otro fabricante.  
  
 En una aplicación o servicio WCF, características de la transacción de WCF proporcionan atributos y configuración para especificar mediante declaración cómo y cuándo la infraestructura debe crear, fluir y sincronizar transacciones.  
  
## <a name="systemtransactions-transactions"></a>Información general sobre las transacciones de System.Transactions  
 El espacio de nombres <xref:System.Transactions> proporciona un modelo de programación explícito según la clase <xref:System.Transactions.Transaction>, así como un modelo de programación implícito utilizando la clase <xref:System.Transactions.TransactionScope>, en la que la infraestructura administra automáticamente las transacciones.  
  
 Para obtener más información sobre cómo crear una aplicación transaccional utilizando estos dos modelos, vea [crear una aplicación transaccional](https://go.microsoft.com/fwlink/?LinkId=94947).  
  
 En una aplicación, o un servicio WCF <xref:System.Transactions> proporciona el modelo de programación para crear las transacciones dentro de una aplicación cliente y para interactuar explícitamente con una transacción, cuando sea necesario, dentro de un servicio.  
  
## <a name="msdtc-transactions"></a>Transacciones de MSDTC  
 Microsoft DTC (Coordinador de transacciones distribuidas) (MSDTC) es un administrador de transacciones que proporciona compatibilidad con transacciones distribuidas.  
  
 Para obtener más información, consulte el [referencia del programador de DTC](https://go.microsoft.com/fwlink/?LinkId=94948).  
  
 En una aplicación o servicio WCF, MSDTC proporciona la infraestructura para la coordinación de transacciones creada dentro de un cliente o servicio.
