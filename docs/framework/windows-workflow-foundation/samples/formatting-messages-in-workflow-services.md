---
title: Dar formato a mensajes en servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
ms.openlocfilehash: eb9a6b3a83a28154dc968bd4c1c41d34028bdd41
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44134797"
---
# <a name="formatting-messages-in-workflow-services"></a>Dar formato a mensajes en servicios de flujo de trabajo
En este ejemplo se muestra cómo se pueden utilizar diferentes tipos de usuario en actividades de mensajería (servicios de WF). El servicio del ejemplo es un servicio de aprobación de gastos simple y expone tres operaciones. `ApproveExpense` toma un tipo de contrato de datos y muestra cómo usar tipos conocidos. La operación devuelve `true` o `false` según la cantidad de gastos. `ApprovePO` toma un tipo XmlSerializer y devuelve `true` o `false` según la cantidad de gastos.`ApprovedVendor` toma un tipo de contrato de mensaje y devuelve `true` o `false` si el proveedor está en la lista de proveedores autorizados o si la solicitud procede del departamento de finanzas (el departamento de finanzas puede usar cualquier proveedor).  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Cargue la solución de proyecto en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y compile el proyecto.  
  
2.  En primer lugar, ejecute el servicio generado en [directorio base de la solución] \FormatterService\bin\debug\  
  
3.  En segundo lugar, ejecute la aplicación Client generada en [directorio base de la solución] \FormatterClient\bin\debug.  
  
4.  El cliente llama a tres operaciones del servicio e imprime los resultados. Cuando se haya completado, presione Entrar para salir del cliente y a continuación del servicio.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`