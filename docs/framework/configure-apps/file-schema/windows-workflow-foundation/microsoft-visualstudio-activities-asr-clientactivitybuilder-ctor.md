---
title: "Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: 
  - "Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor"
apilocation: 
  - "Microsoft.VisualStudio.Activities.dll"
apitype: "Assembly"
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
Crea una instancia de la clase [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md).  
  
## Sintaxis  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
  
```  
  
#### Parámetros  
  
## Valores de parámetros  
 *operationDescription*  
  
 Describe la operación que se va a realizar en la actividad de flujo de trabajo que se va a generar, incluidos el nombre de la operación, el tipo devuelto y la información de parámetros.  El valor de este parámetro no debe ser **null**.  Debe describir una operación sincrónica que use un contrato de mensaje y tome un argumento con un mensaje.  Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.  
  
 *configurationName*  
  
 Especifica el nombre de configuración del extremo.  El valor de este parámetro no debe ser **null** o estar vacío.  Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.  
  
 *proxyNamespace*  
  
 Especifica el espacio de nombres de servicio para la operación.  El valor de este parámetro no debe ser **null** o estar vacío.  Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.  
  
## Vea también  
 [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)