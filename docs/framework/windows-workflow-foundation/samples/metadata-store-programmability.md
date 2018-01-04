---
title: "Capacidad de programación del almacén de metadatos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b8bfce17169a1095d2d2817467fcc8f3366ead3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="metadata-store-programmability"></a>Capacidad de programación del almacén de metadatos
El almacén de metadatos es una característica de [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] que permite la asociación de metadatos arbitrarios, en forma de atributos de CLR, con tipos en tiempo de ejecución. Esto permite un acoplamiento separado entre los componentes de tiempo de ejecución y sus homólogos en tiempo de diseño, así como la capacidad de cambiar los componentes en tiempo de diseño sin afectar al tiempo de ejecución. En este ejemplo se muestra cómo realizar una programación en el almacén de metadatos aplicando atributos a un tipo en tiempo de ejecución, sobre cuyo origen no tenemos control alguno. La terminología normalmente utilizada es que una aplicación de hospedaje registra los metadatos para un conjunto de tipos.  
  
 En la salida, puede observar un atributo adicional inesperado, <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`. Este atributo se agrega al utilizar la API de metadatos y no tiene ningún impacto en la ejecución del ejemplo.  
  
 En este ejemplo se explica cómo:  
  
## <a name="demonstrates"></a>Demostraciones  
  
-   Inyección de atributos utilizando la API del almacén de metadatos.  
  
-   Uso de un mecanismo de devolución de llamada para diferir el registro de metadatos.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución ProgrammingMetadataStore.sln.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Presione F5 para ejecutar la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`