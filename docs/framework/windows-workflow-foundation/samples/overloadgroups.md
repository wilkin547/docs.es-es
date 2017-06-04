---
title: "OverloadGroups | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# OverloadGroups
Este ejemplo consta de una actividad \(`CreateLocation`\), que tiene dos características interesantes:  
  
1.  Tiene algunos argumentos necesarios y algunos opcionales.  
  
2.  Permite al usuario optar por uno de dos conjuntos de argumentos.  
  
 Estos comportamientos se logran utilizando estas dos características:  
  
-   `[isRequired]` valida si se ha asignado una propiedad de una actividad concreta, y si no, produce una excepción.  
  
-   `[OverloadGroup]` reúne un conjunto de argumentos para que el usuario de la actividad pueda elegir entre utilizar un conjunto u otro.El usuario no puede utilizar argumentos de diferentes grupos de sobrecarga en la misma instancia.  
  
 Después de configurar diferentes flujos de trabajo, llame al método <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> que devuelve una colección <xref:System.Activities.Validation.ValidationResults> de <xref:System.Activities.Validation.ConstraintViolation>.Imprima los objetos <xref:System.Activities.Validation.ConstraintViolation> en la consola.  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la solución de ejemplo **OverloadGroups.sln** en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile y ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`  
  
## Vea también