---
title: Implementación de aplicaciones WCF con ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: b520931751bbba00d440b46657962ad3f1e41cd3
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802235"
---
# <a name="deploying-wcf-applications-with-clickonce"></a>Implementación de aplicaciones WCF con ClickOnce
Las aplicaciones cliente que usan Windows Communication Foundation (WCF) se pueden implementar mediante la tecnología ClickOnce. Esta tecnología les permite sacar partido de las protecciones de seguridad en tiempo de ejecución proporcionadas por seguridad de acceso del código (CAS), siempre que estén firmadas digitalmente con un certificado de confianza. El certificado utilizado para firmar la aplicación ClickOnce debe residir en el almacén del Editor de confianza y la directiva de seguridad local en el equipo cliente se debe configurar para conceder los permisos de plena confianza a las aplicaciones firmadas con el certificado del editor.  
  
 Para obtener información sobre la configuración de aplicaciones ClickOnce y editores de confianza, vea [configurar editores de confianza de ClickOnce](https://docs.microsoft.com/previous-versions/dotnet/articles/ms996418(v=msdn.10)).  
  
## <a name="see-also"></a>Vea también

- [Introducción a la implementación de aplicaciones de confianza](/visualstudio/deployment/trusted-application-deployment-overview)
- [Implementación de ClickOnce para aplicaciones de Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/wh45kb66(v=vs.90))
