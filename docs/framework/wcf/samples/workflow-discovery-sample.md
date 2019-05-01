---
title: Ejemplo de detección de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
ms.openlocfilehash: 9a0d3ad22b4663ee71b5b2aa8d0e3d64f20996d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006465"
---
# <a name="workflow-discovery-sample"></a>Ejemplo de detección de flujo de trabajo
En este ejemplo se muestra cómo hacer que un servicio de flujo de trabajo se pueda detectar y cómo crear una actividad de código personalizada que busque un servicio determinado.  
  
## <a name="demonstrates"></a>Demostraciones  
 Actividad de búsqueda de detección y uso del flujo de trabajo  
  
## <a name="discussion"></a>Discusión  
 En la primera parte del ejemplo, se hace que un servicio de flujo de trabajo se pueda detectar mediante la configuración. La configuración también se puede utilizar para aplicar el servicio de forma apropiada con los metadatos personalizados (como los ámbitos). En el cliente, el ejemplo utiliza una actividad de código personalizada, que utiliza Detección para buscar un servicio que coincide con un contrato determinado. La actividad de código genera un URI, que se utiliza después en una actividad de envío.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. En este ejemplo utiliza los extremos HTTP, que deben tener las ACL de dirección URL apropiadas para ejecutarse (vea [configurar HTTP y HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) para obtener más información). Al ejecutar el siguiente comando en un símbolo del sistema con permisos elevados, se deberían agregar las ACL adecuadas. Sustituya su dominio y nombre de usuario para los siguientes argumentos si su shell no entiende el formato de variable.  
  
     **netsh http agregar urlacl url =http://+:8000/ usuario = % DOMAIN %\\% UserName %**  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
