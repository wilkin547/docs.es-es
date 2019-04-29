---
title: Procedimiento para habilitar el servicio de uso compartido de puertos Net.TCP
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 20db0ef427a5e791bd6b8dcef90bf7911ae0d4a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772962"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a>Procedimiento para habilitar el servicio de uso compartido de puertos Net.TCP
Windows Communication Foundation (WCF) utiliza un servicio de Windows denominado el servicio de uso compartido de puertos Net.TCP para facilitar el uso compartido de puertos TCP entre varios procesos. Este servicio se instala como parte de WCF, pero el servicio no está habilitado de forma predeterminada como precaución de seguridad y por lo que debe habilitarse manualmente antes de usarse por primera vez. En este tema se describe cómo configurar el Servicio de uso compartido de puertos Net.TCP mediante el complemento de Microsoft Management Console (MMC).  
  
 Después de habilitar el servicio de uso compartido de puertos Net.TCP y lo inicie manualmente, vea [Cómo: Configurar un servicio de WCF para utilizar el uso compartido de puertos](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) para obtener información sobre cómo configurar el servicio para utilizar este servicio.  
  
 Para obtener un ejemplo que utiliza el uso compartido de puertos net.tcp://, vea el [ejemplo de uso compartido de puertos Net.TCP](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a>Habilitación del servicio de uso compartido de puertos Net.TCP mediante MMC  
  
1. En el menú Inicio, abra la consola de administración de servicios, ya sea abriendo una ventana del símbolo del sistema y escribiendo `services.msc` o abriendo ejecutar y escribiendo `services.msc` en el cuadro Abrir.  
  
2. En el **nombre** columna de la lista de servicios, haga clic en el **servicio de uso compartido de puertos Net.Tcp**y seleccione **propiedades** en el menú.  
  
3. Para habilitar el inicio manual del servicio, en el **propiedades** ventana Seleccione el **General** ficha y en el **tipo de inicio** seleccione Manual y, a continuación, haga clic en **Aplicar**.  
  
4. Para iniciar el servicio, en el área de estado del servicio, haga clic en el **iniciar** botón. El estado del servicio debería mostrar ahora "Iniciado".  
  
5. Para volver a la lista de servicios, haga clic en el **Aceptar**y salga de la consola de MMC.  
  
## <a name="example"></a>Ejemplo  
  
## <a name="see-also"></a>Vea también

- [Uso compartido de puertos Net.TCP](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)
- [Configuración del servicio de uso compartido de puertos Net.TCP](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
