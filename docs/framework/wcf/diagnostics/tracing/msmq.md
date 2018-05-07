---
title: MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 5e157da25829a0741de988d1d6dde0318a93b109
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="msmq"></a>MSMQ
En una aplicación MSMQ, no se transfiere ninguna actividad adicional del canal en cola a MSMQ y de MSMQ al canal en cola.  
  
 Además, se siguen tanto el id. de mensaje de MSMQ como el del mensaje SOAP (junto con el id. de la actividad, si existe) como seguimientos de canal en cola en una operación de envío.  
  
 Se siguen tanto el id. de mensaje de MSMQ como el del mensaje SOAP (junto con el id. de la actividad, si existe) como seguimientos de canal en cola en una operación de recepción.  
  
 Las transferencias necesarias en la operación de recepción se ejecutan de igual forma que en cualquier otro transporte (operación de recepción de bytes ->Procese mensaje ->).
