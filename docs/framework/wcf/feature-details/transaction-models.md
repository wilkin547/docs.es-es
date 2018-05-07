---
title: Modelos de transacción
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 9efe8c6994cc80957b707bbae0885a3c5896f70a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="transaction-models"></a>Modelos de transacción
En este tema se describe la relación entre los modelos de programación de la transacción y los componentes de infraestructura que Microsoft proporciona.  
  
 Cuando se usan transacciones en Windows Communication Foundation (WCF), es importante comprender que son no seleccionando entre modelos transaccionales diferentes, sino operando en diferentes capas de un modelo integrado y coherente.  
  
 Las secciones siguientes describen los tres componentes de transacción primarios.  
  
## <a name="windows-communication-foundation-transactions"></a>Transacciones de Windows Communication Foundation  
 La compatibilidad con transacciones en WCF le permite que escribir servicios transaccionales. Además, con su compatibilidad para el protocolo de WS-AtomicTransaction (WS-AT), las aplicaciones pueden fluir transacciones a servicios Web creados con WCF o tecnología de otro fabricante.  
  
 En una aplicación o servicio WCF, características de la transacción de WCF proporcionan atributos y configuración para especificar de manera declarativa cómo y cuándo la infraestructura debe crear, fluir y sincronizar transacciones.  
  
## <a name="systemtransactions-transactions"></a>Información general sobre las transacciones de System.Transactions  
 El espacio de nombres <xref:System.Transactions> proporciona un modelo de programación explícito según la clase <xref:System.Transactions.Transaction>, así como un modelo de programación implícito utilizando la clase <xref:System.Transactions.TransactionScope>, en la que la infraestructura administra automáticamente las transacciones.  
  
 Para obtener más información acerca de cómo crear una aplicación transaccional mediante estos dos modelos, vea [escribir una aplicación transaccional](http://go.microsoft.com/fwlink/?LinkId=94947).  
  
 En un servicio WCF o una aplicación, <xref:System.Transactions> proporciona el modelo de programación para crear las transacciones dentro de una aplicación de cliente y para interactuar explícitamente con una transacción, cuando se requiera, dentro de un servicio.  
  
## <a name="msdtc-transactions"></a>Transacciones de MSDTC  
 Microsoft DTC (Coordinador de transacciones distribuidas) (MSDTC) es un administrador de transacciones que proporciona compatibilidad con transacciones distribuidas.  
  
 Para obtener más información, consulte el [referencia del programador de DTC](http://go.microsoft.com/fwlink/?LinkId=94948).  
  
 En una aplicación o servicio WCF, MSDTC proporciona la infraestructura para la coordinación de transacciones creada dentro de un cliente o servicio.
