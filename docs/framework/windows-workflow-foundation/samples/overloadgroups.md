---
title: OverloadGroups
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f644f09af3ce9e191dc6c5680472de4ef5ab727d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="overloadgroups"></a>OverloadGroups
Este ejemplo consta de una actividad (`CreateLocation`), que tiene dos características interesantes:  
  
1.  Tiene algunos argumentos necesarios y algunos opcionales.  
  
2.  Permite al usuario optar por uno de dos conjuntos de argumentos.  
  
 Estos comportamientos se logran utilizando estas dos características:  
  
-   `[isRequired]` valida si se ha asignado una propiedad de una actividad concreta, y si no, produce una excepción.  
  
-   `[OverloadGroup]` reúne un conjunto de argumentos para que el usuario de la actividad pueda elegir entre utilizar un conjunto u otro. El usuario no puede utilizar argumentos de diferentes grupos de sobrecarga en la misma instancia.  
  
 Después de configurar diferentes flujos de trabajo, llame al método <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> que devuelve una colección <xref:System.Activities.Validation.ValidationResults> de <xref:System.Activities.Validation.Constraint>. Imprima los objetos <xref:System.Activities.Validation.Constraint> en la consola.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la **OverloadGroups.sln** solución en de ejemplo [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile y ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
