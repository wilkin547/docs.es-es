---
description: 'Más información acerca de: 1148-FlowchartSwitchCaseNotFound'
title: 1148 - FlowchartSwitchCaseNotFound
ms.date: 03/30/2017
ms.assetid: 9ee7fcee-e040-4306-968e-ed840a1cb00c
ms.openlocfilehash: 067dff850a67f1b235bf9c1903757eefa912bd92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720415"
---
# <a name="1148---flowchartswitchcasenotfound"></a>1148 - FlowchartSwitchCaseNotFound

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1148|  
|Palabras clave|WFActivities|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que no se pudo encontrar ni un caso correspondiente ni un caso predeterminado en un modificador de diagrama de flujo. La ejecución del diagrama de flujo va a finalizar.  
  
## <a name="message"></a>Message  

 Flowchart '%1'/FlowSwitch no puede encontrar una actividad Case ni un caso predeterminado que coincida con el resultado de la expresión. La ejecución del diagrama de flujo va a finalizar.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Diagrama de flujo|xs:string|El nombre para mostrar del diagrama de flujo.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
