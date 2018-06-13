---
title: Codificador de ByteStream
ms.date: 03/30/2017
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
ms.openlocfilehash: ab9ccf47527dcf7f01f272f09b3b341d30fbd8d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499685"
---
# <a name="bytestream-encoder"></a>Codificador de ByteStream
Este ejemplo muestra cómo crear un objeto `ByteStreamHttpBinding`, <xref:System.ServiceModel.Channels.Binding> que ilustra la funcionalidad del codificador del flujo de bytes.  
  
## <a name="discussion"></a>Explicación  
 En este ejemplo se muestra cómo crear un objeto <xref:System.ServiceModel.Channels.Binding> estándar mediante los elementos de enlace estándar <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> y <xref:System.ServiceModel.Channels.HttpTransportBindingElement>. En este ejemplo se muestra cómo utilizar el codificador de flujo de bytes para cargar y descargar una imagen. La característica de codificador de flujo de bytes solo admite el transporte HTTP y no admite características como la mensajería de confianza o la seguridad. La única <xref:System.ServiceModel.Channels.MessageVersion> que se admite es la propiedad <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.  
  
> [!IMPORTANT]
>  Si va a ejecutar este ejemplo en [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] o [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], asegúrese de que va a ejecutar [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] con privilegios elevados.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra el archivo ByteStreamHttpBinding.sln en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Inicie una nueva instancia del proyecto ByteStreamHttpBindingServer haciendo clic en el proyecto en el Explorador de soluciones y seleccionando **depurar**y, a continuación, **Iniciar nueva instancia** en el menú contextual.  
  
3.  Inicie una nueva instancia del proyecto ByteStreamHttpBindingClient haciendo clic en el proyecto en el Explorador de soluciones y seleccionando **depurar**, **Iniciar nueva instancia** en el menú contextual.
