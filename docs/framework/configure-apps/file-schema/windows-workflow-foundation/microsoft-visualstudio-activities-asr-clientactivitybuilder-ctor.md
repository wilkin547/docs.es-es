---
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
ms.openlocfilehash: 0ce9be30182f9181bcb6449529d9b9796aadbc2b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133541"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a>Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
Crea una instancia de la [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) clase.  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a>Parámetros  
  
## <a name="parameter-values"></a>Valores de parámetros  
 *operationDescription*  
  
 Describe la operación que se va a realizar en la actividad de flujo de trabajo que se va a generar, incluidos el nombre de la operación, el tipo devuelto y la información de parámetros. El valor de este parámetro no debe ser **null**. Debe describir una operación sincrónica que use un contrato de mensaje y tome un argumento con un mensaje. Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.  
  
 *configurationName*  
  
 Especifica el nombre de configuración del extremo. El valor de este parámetro no debe ser **null** o está vacío. Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.  
  
 *proxyNamespace*  
  
 Especifica el espacio de nombres de servicio para la operación. El valor de este parámetro no debe ser **null** o está vacío. Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.  
  
## <a name="see-also"></a>Vea también

- [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
