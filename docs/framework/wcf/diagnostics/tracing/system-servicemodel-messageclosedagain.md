---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: a8aa5e600789df1b64a8a3f1a6355aaae6a6cf4b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294435"
---
# <a name="systemservicemodelmessageclosedagain"></a>System.ServiceModel.MessageClosedAgain

System.ServiceModel.MessageClosedAgain  
  
## <a name="description"></a>Descripción  

 Se cerró un mensaje de nuevo.  
  
 Un mensaje debería cerrarse solo una vez. Si este seguimiento se emite en código de extensión de usuario, indica que el código de extensión de usuario está cerrando un mensaje que ya se ha cerrado. Si este seguimiento se emite a través del código de producto, indica que el código de extensión de usuario podría estar cerrando un mensaje antes de tiempo.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
