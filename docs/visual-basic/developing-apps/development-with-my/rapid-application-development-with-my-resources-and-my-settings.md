---
title: "Desarrollo r&#225;pido de aplicaciones con My.Resources y My.Settings (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Resources (objeto), desarrollar aplicaciones"
  - "My.Settings (objeto), desarrollar aplicaciones"
  - "desarrollo rápido de aplicaciones (RAD), My.Resources"
  - "desarrollo rápido de aplicaciones (RAD), My.Settings"
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Desarrollo r&#225;pido de aplicaciones con My.Resources y My.Settings (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El objeto `My.Resources` proporciona acceso a los recursos de la aplicación y permite recuperar dinámicamente los recursos de su aplicación.  
  
## Recuperar recursos  
 Diferentes recursos como archivos de sonido, iconos, imágenes y cadenas se pueden recuperar a través del objeto `My.Resources`.  Por ejemplo, puede tener acceso a los archivos de recursos específicos de la referencia cultural de la aplicación.  El siguiente ejemplo establece el icono del formulario en el icono denominado `Form1Icon` almacenado en el archivo de recursos de la aplicación.  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 El objeto `My.Resources` expone sólo recursos globales.  No proporciona acceso a archivos de recursos asociados a formularios.  Debe tener acceso a los recursos de formulario de los formularios.  Para obtener más información, vea [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/es-es/9a96220d-a19b-4de0-9f48-01e5d82679e5).  
  
 De la misma forma, el objeto `My.Settings` proporciona acceso a la configuración de la aplicación y permite almacenar y recuperar de forma dinámica valores de propiedades y otra información relativa a la aplicación.  Para obtener más información, vea [My.Resources \(Objeto\)](../../../visual-basic/language-reference/objects/my-resources-object.md) y [My.Settings \(Objeto\)](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## Vea también  
 [My.Resources \(Objeto\)](../../../visual-basic/language-reference/objects/my-resources-object.md)   
 [My.Settings \(Objeto\)](../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Acceso a la configuración de la aplicación.](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)