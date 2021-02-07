---
description: 'Más información acerca de: Microsoft. VisualStudio. Activities. ASR. ClientActivityBuilder.. ctor'
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.date: 03/30/2017
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
ms.openlocfilehash: 1a1b436c2b15fdf07f924aa0db2a13598422e988
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739994"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a>Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor

Crea una instancia de la clase [Microsoft. VisualStudio. Activities. ASR. ClientActivityBuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a>Parámetros  
  
## <a name="parameter-values"></a>Valores de parámetros  

 *operationDescription*  
  
 Describe la operación que se va a realizar en la actividad de flujo de trabajo que se va a generar, incluidos el nombre de la operación, el tipo devuelto y la información de parámetros. El valor de este parámetro no debe ser **null**. Debe describir una operación sincrónica que use un contrato de mensaje y tome un argumento con un mensaje. Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.  
  
 *configurationName*  
  
 Especifica el nombre de configuración del extremo. El valor de este parámetro no debe ser **null** ni estar vacío. Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.  
  
 *proxyNamespace*  
  
 Especifica el espacio de nombres de servicio para la operación. El valor de este parámetro no debe ser **null** ni estar vacío. Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.  
  
## <a name="see-also"></a>Vea también

- [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
