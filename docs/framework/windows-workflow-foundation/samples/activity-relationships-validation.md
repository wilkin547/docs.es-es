---
title: Validar relaciones de actividad
ms.date: 03/30/2017
ms.assetid: 6f11a34e-ed67-4bce-88ce-7e96bbb4d052
ms.openlocfilehash: e6dd0e6a7b48444073ebae378e21c1b45977a1f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515113"
---
# <a name="activity-relationships-validation"></a>Validar relaciones de actividad
Este ejemplo consta de tres actividades, `CreateCity`, `CreateState` y `CreateCountry`. `CreateCity` debe estar dentro de una actividad `CreateState` y `CreateState` debe estar dentro de una actividad `CreateCountry`. Para este ejemplo, la lógica de validación está en código para la actividad `CreateState` y en XAML para la actividad `CreateCity`. Ambas restricciones tienen el mismo comportamiento.  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] proporciona las tres actividades auxiliares siguientes que permiten al desarrollador validar las relaciones entre las actividades.  
  
 <xref:System.Activities.Validation.GetParentChain>  
 Proporciona la colección de todas las actividades que pertenecen al elemento primario del nodo actual  
  
 <xref:System.Activities.Validation.GetChildSubtree>  
 Proporciona la colección de todas las actividades que pertenecen al subárbol del nodo actual, excluido el nodo actual  
  
 <xref:System.Activities.Validation.GetWorkflowTree>  
 Proporciona la colección de todas las actividades incluidas en el mismo árbol que el nodo actual  
  
 En el ejemplo, se usa una actividad <xref:System.Activities.Statements.ForEach%601> para recorrer la colección que devuelve <xref:System.Activities.Validation.GetParentChain>. En cada elemento de la colección, su tipo se compara con `CreateCountry` (o `CreateState` si se está validando `CreateCity`); y cuando se encuentra una coincidencia, la marca de resultado se establece en `true`. Finalmente, <xref:System.Activities.Validation.AssertValidation> se utiliza para generar un error de validación si la marca del resultado se establece en `false`.  
  
### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra la solución de ejemplo ContainmentValidation.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile la solución.  
  
3.  Presione CTRL + F5 para iniciar el programa.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ActivityRelationships`
