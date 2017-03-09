---
title: "Refactorizaci&#243;n y Cambiar nombre (Cuadro de di&#225;logo) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.RenameSymbol"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "símbolos, cambiar nombre"
  - "nombres, cambiar símbolo"
  - "Cambiar nombre (cuadro de diálogo)"
ms.assetid: 001d2d81-9bb6-4e8e-ae3a-20c0daaa3959
redirect_url: https://msdn.microsoft.com/library/ckfya594(v=vs.140).aspx
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Refactorizaci&#243;n y Cambiar nombre (Cuadro de di&#225;logo) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Utilice el cuadro de diálogo integrado **Cambiar nombre** de Visual Basic para cambiar el nombre de los identificadores usados en el código para símbolos como campos, variables locales, métodos, espacios de nombres, propiedades y tipos.  Para abrir el cuadro de diálogo **Cambiar nombre**, haga clic con el botón secundario del mouse en la declaración del elemento.  
  
 **Nuevo nombre**  
 Especifica el nuevo nombre para el elemento de código.  
  
 **Ubicación**  
 Identifica el espacio de nombres que debe buscarse al realizar la operación de cambio de nombre.  
  
## Operaciones de cambio de nombre  
 El cuadro de diálogo **Cambiar nombre** realiza operaciones de cambio de nombre ligeramente distintas, dependiendo del tipo del elemento cuyo nombre se va a cambiar.  
  
|Tipo de elemento|Operación de cambio de nombre|  
|----------------------|-----------------------------------|  
|Clase|Cambia todas las declaraciones y todos los usos de la clase por el nuevo nombre.  Para las clases parciales, la operación de cambio de nombre se propaga a todas las partes donde aparece.|  
|Campo|Cambia la declaración y los usos del campo al nuevo nombre.|  
|Variable local|Cambia la declaración y los usos de la variable por el nuevo nombre.|  
|Método|Cambia el nombre del método y todas las referencias a ese método al nuevo nombre.|  
|Espacio de nombres|Cambia el nombre del espacio de nombres al nuevo nombre en la declaración, en todas las instrucciones `Imports` y en todos los nombres completos.|  
|Propiedad.|Cambia la declaración y los usos de la propiedad al nuevo nombre.|  
  
## Refactorización  
 Para proporcionar una experiencia de refactorización completa, Visual Basic se ha asociado con Developer Express Inc.  para obtener la compatibilidad de refactorización.  Vea [Refactor\!](http://go.microsoft.com/fwlink/?LinkId=155788) en el Centro para desarrolladores de Visual Basic en MSDN para obtener más información e instrucciones sobre cómo descargar esta herramienta.  Refactor\!  admite más de 15 características de refactorización individuales.  Entre estas características se incluyen operaciones como Reordenar parámetros, Extraer método, Encapsular campo y Crear sobrecarga.  
  
## Vea también  
 [Utilizar el entorno de desarrollo de Visual Basic](../../../visual-basic/developing-apps/using-ide/using-the-visual-basic-development-environment.md)