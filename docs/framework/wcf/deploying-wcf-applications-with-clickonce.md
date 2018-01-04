---
title: "Implementación de aplicaciones WCF con ClickOnce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e87e01c39c5f50ff3f4d4e9479a68e19cceb90f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-wcf-applications-with-clickonce"></a>Implementación de aplicaciones WCF con ClickOnce
Las aplicaciones cliente que usen [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] se pueden implementar utilizando la tecnología de ClickOnce. Esta tecnología les permite sacar partido de las protecciones de seguridad en tiempo de ejecución proporcionadas por seguridad de acceso del código (CAS), siempre que estén firmadas digitalmente con un certificado de confianza. El certificado utilizado para firmar la aplicación ClickOnce debe residir en el almacén del Editor de confianza y la directiva de seguridad local en el equipo cliente se debe configurar para conceder los permisos de plena confianza a las aplicaciones firmadas con el certificado del editor.  
  
 Para obtener información acerca de cómo configurar las aplicaciones ClickOnce y editores de confianza, consulte [Configurar editores de confianza de ClickOnce](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a la implementación de aplicaciones de confianza](http://go.microsoft.com/fwlink/?LinkId=94775)  
 [Las aplicaciones de implementación de ClickOnce para Windows Forms](http://go.microsoft.com/fwlink/?LinkId=94776)
