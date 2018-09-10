---
title: Aislamiento de red para aplicaciones de la Tienda Windows
ms.date: 03/30/2017
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4d26b6df5d26a96bb8fa41dd3a8151fcb4a08b75
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43773662"
---
# <a name="network-isolation-for-windows-store-apps"></a>Aislamiento de red para aplicaciones de la Tienda Windows
Es posible usar las clases de los espacios de nombres <xref:System.Net>, <xref:System.Net.Http> y <xref:System.Net.Http.Headers> para desarrollar aplicaciones de la Tienda Windows o aplicaciones de escritorio. Cuando se usan en una aplicación de la Tienda Windows, las clases de estos espacios de nombres se ven afectadas por el aislamiento de red, que forma parte del modelo de seguridad para las aplicaciones usado por [!INCLUDE[win8](../../../includes/win8-md.md)]. Las funcionalidades de red correspondientes deben estar habilitadas en el manifiesto de la aplicación de la Tienda Windows para que el sistema permita el acceso a la red.  
  
## <a name="checklist-for-network-isolation"></a>Lista de comprobación para el aislamiento de red  
 Use esta lista de comprobación para asegurarse de que el aislamiento de red está configurado para la aplicación de la Tienda Windows.  
  
1.  Determine la dirección de las solicitudes de acceso a la red que necesita la aplicación. Puede tratarse de solicitudes salientes iniciadas por el cliente, solicitudes entrantes no solicitadas o una combinación de ambos tipos de solicitudes de red.  
  
2.  Determine el tipo de recursos de red con los que se comunicará la aplicación. Una aplicación podría tener que comunicarse con recursos de confianza en una red doméstica o de trabajo. Una aplicación podría tener que comunicarse con recursos de Internet. Una aplicación podría necesitar tener acceso a ambos tipos de recursos de red.  
  
3.  Configure las funcionalidades mínimas necesarias de aislamiento de red en el manifiesto de la aplicación.  
  
4.  Implemente y ejecute la aplicación para probarla mediante las herramientas de aislamiento de red proporcionadas para la solución de problemas.  
  
 Para obtener más información sobre cómo configurar las funcionalidades de red y las herramientas de aislamiento que se usan para la solución de problemas de aislamiento de red, vea [Cómo configurar las funcionalidades de aislamiento de red](https://go.microsoft.com/fwlink/?LinkID=228265) en la documentación para desarrolladores de [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Conectar con un servicio web](https://go.microsoft.com/fwlink/?LinkID=245696)  
 [Directrices y lista de comprobación para el aislamiento de red](https://go.microsoft.com/fwlink/?LinkID=228265)  
 [Inicio rápido: conectarse mediante HttpClient](https://go.microsoft.com/fwlink/?LinkId=245697)  
 [Cómo usar controladores HttpClient](https://go.microsoft.com/fwlink/?LinkId=245699)  
 [Cómo proteger conexiones HttpClient](https://go.microsoft.com/fwlink/?LinkId=245698)  
 [Ejemplo de HttpClient](https://go.microsoft.com/fwlink/?LinkId=242550)
