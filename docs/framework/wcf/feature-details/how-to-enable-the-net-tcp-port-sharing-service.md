---
title: Procedimiento para habilitar el servicio de uso compartido de puertos Net.TCP
description: Obtenga información acerca de cómo configurar el servicio de uso compartido de puertos net TCP mediante MMC para habilitar net. TCP, que está deshabilitado de forma predeterminada.
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 0292559e3befde7f0b00b36aa10a2d9615daf049
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247005"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a>Procedimiento para habilitar el servicio de uso compartido de puertos Net.TCP
Windows Communication Foundation (WCF) usa un servicio de Windows denominado servicio de uso compartido de puertos net. TCP para facilitar el uso compartido de puertos TCP en varios procesos. Este servicio se instala como parte de WCF, pero el servicio no está habilitado de forma predeterminada como precaución de seguridad y, por lo tanto, debe habilitarse manualmente antes de usarse por primera vez. En este tema se describe cómo configurar el Servicio de uso compartido de puertos Net.TCP mediante el complemento de Microsoft Management Console (MMC).  
  
 Después de habilitar el servicio de uso compartido de puertos net. TCP e iniciarlo manualmente, consulte [Cómo: configurar un servicio WCF para usar el uso compartido de puertos](how-to-configure-a-wcf-service-to-use-port-sharing.md) para obtener información sobre cómo configurar el servicio para utilizar este servicio.  
  
 Para obtener un ejemplo que usa net. TCP://uso compartido de puertos, consulte el [ejemplo de uso compartido de puertos net. TCP](../samples/net-tcp-port-sharing-sample.md).  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a>Habilitación del servicio de uso compartido de puertos Net.TCP mediante MMC  
  
1. En el menú Inicio, abra la consola de administración de servicios; para ello, abra una ventana del símbolo del sistema y escriba `services.msc` o abra ejecutar y escriba `services.msc` en el cuadro Abrir.  
  
2. En la columna **nombre** de la lista de servicios, haga clic con el botón secundario en el **servicio de uso compartido de puertos net. TCP**y seleccione **propiedades** en el menú.  
  
3. Para habilitar el inicio manual del servicio, en la ventana **propiedades** , seleccione la pestaña **General** y, en el cuadro **tipo de inicio** , seleccione manual y, a continuación, haga clic en **aplicar**.  
  
4. Para iniciar el servicio, en el área estado del servicio, haga clic en el botón **iniciar** . El estado del servicio debería mostrar ahora "Iniciado".  
  
5. Para volver a la lista de servicios, haga clic en **Aceptar**y salga de la consola MMC.  
  
## <a name="example"></a>Ejemplo  
  
## <a name="see-also"></a>Vea también

- [Uso compartido de puertos Net.TCP](net-tcp-port-sharing.md)
- [Configuración del servicio de uso compartido de puertos Net.TCP](configuring-the-net-tcp-port-sharing-service.md)
