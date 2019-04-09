---
title: Implementación de aplicaciones WCF con ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: 1820b00aa903633750f74f319f9cf8038ba2b043
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086239"
---
# <a name="deploying-wcf-applications-with-clickonce"></a>Implementación de aplicaciones WCF con ClickOnce
Las aplicaciones cliente mediante Windows Communication Foundation (WCF) se pueden implementar mediante la tecnología ClickOnce. Esta tecnología les permite sacar partido de las protecciones de seguridad en tiempo de ejecución proporcionadas por seguridad de acceso del código (CAS), siempre que estén firmadas digitalmente con un certificado de confianza. El certificado utilizado para firmar la aplicación ClickOnce debe residir en el almacén del Editor de confianza y la directiva de seguridad local en el equipo cliente se debe configurar para conceder los permisos de plena confianza a las aplicaciones firmadas con el certificado del editor.  
  
 Para obtener información sobre cómo configurar las aplicaciones ClickOnce y editores de confianza, consulte [Configuring ClickOnce Trusted Publishers](https://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre la implementación de aplicaciones de confianza](https://go.microsoft.com/fwlink/?LinkId=94775)
- [Las aplicaciones de implementación de ClickOnce para Windows Forms](https://go.microsoft.com/fwlink/?LinkId=94776)
