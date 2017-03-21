---
title: /codepage (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 90dce6e34e52862807e2acdbf1850699316730d1
ms.lasthandoff: 03/13/2017

---
# <a name="codepage-visual-basic"></a>/codepage (Visual Basic)
Especifica la página de códigos que se va a utilizar para todos los archivos de código fuente en la compilación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/codepage:id  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`id`|Obligatorio. El compilador utiliza la página de códigos especificada por `id` para interpretar la codificación de los archivos de origen.|  
  
## <a name="remarks"></a>Comentarios  
 Para compilar código fuente guardado con una codificación específica, puede utilizar `/codepage` para especificar la página de códigos que debe utilizarse. El `/codepage` opción se aplica a todos los archivos de código fuente de la compilación. Para obtener más información, consulte [la codificación de caracteres en .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).  
  
 El `/codepage` opción no es necesaria si los archivos de código fuente se guardaron utilizando la página de códigos ANSI actual, Unicode o UTF-8 con una firma. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]guarda todos los archivos de código fuente con la página de códigos ANSI actual de forma predeterminada, a menos que el usuario especifique otra codificación en el **codificación** cuadro de diálogo. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]usa el **codificación** cuadro de diálogo para abrir archivos de código fuente guardados con una página de códigos diferente.  
  
> [!NOTE]
>  El `/codepage` opción no está disponible en la [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] entorno de desarrollo; está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
