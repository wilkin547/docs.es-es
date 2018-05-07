---
title: Cómo habilitar el servicio de uso compartido de puertos Net.TCP
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 4b5a18e11d9fc15f23b5353883a63d838face58a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a>Cómo habilitar el servicio de uso compartido de puertos Net.TCP
Windows Communication Foundation (WCF) utiliza un servicio de Windows denominado el servicio de uso compartido de puertos Net.TCP para facilitar el uso compartido de puertos TCP entre varios procesos. Este servicio se instala como parte de WCF, pero el servicio no está habilitado de forma predeterminada como precaución de seguridad y por lo que debe habilitarse manualmente antes de utilizarlo por primera vez. En este tema se describe cómo configurar el Servicio de uso compartido de puertos Net.TCP mediante el complemento de Microsoft Management Console (MMC).  
  
 Después de habilitar el servicio de uso compartido de puertos Net.TCP e iniciarla manualmente, consulte [Cómo: configurar un servicio de WCF para utilizar el uso compartido de puertos](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) para obtener información acerca de cómo configurar el servicio para utilizar este servicio.  
  
 Para obtener un ejemplo que utiliza el uso compartido de puertos net.tcp://, consulte el [ejemplo de uso compartido de puertos Net.TCP](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a>Habilitación del servicio de uso compartido de puertos Net.TCP mediante MMC  
  
1.  En el menú Inicio, abra la consola de administración de servicios, ya sea abriendo una ventana de símbolo del sistema y escribiendo `services.msc` o abriendo ejecutar y escriba `services.msc` en el cuadro Abrir.  
  
2.  En el **nombre** columna de la lista de servicios, haga clic en el **servicio de uso compartido de puertos Net.Tcp**y seleccione **propiedades** en el menú.  
  
3.  Para habilitar el inicio manual del servicio, en la **propiedades** ventana Seleccione la **General** ficha y en el **tipo de inicio** seleccione Manual y, a continuación, haga clic en **Aplicar**.  
  
4.  Para iniciar el servicio, en el área de estado de servicio, haga clic en el **iniciar** botón. El estado del servicio debería mostrar ahora "Iniciado".  
  
5.  Para volver a la lista de servicios, haga clic en el **Aceptar**y salga de la consola de MMC.  
  
## <a name="example"></a>Ejemplo  
  
## <a name="see-also"></a>Vea también  
 [Uso compartido de puertos Net.TCP](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [Configuración del servicio de uso compartido de puertos Net.TCP](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
