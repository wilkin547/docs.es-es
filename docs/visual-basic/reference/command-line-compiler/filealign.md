---
title: /filealign | Documentos de Microsoft
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
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: 14
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
ms.openlocfilehash: 18d5c3e327e2e41f4786eda6c3e981125f87389d
ms.lasthandoff: 03/13/2017

---
# <a name="filealign"></a>/filealign
Especifica dónde se alinean las secciones del archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/filealign:number  
```  
  
## <a name="arguments"></a>Argumentos  
 `number`  
 Obligatorio. Un valor que especifica la alineación de secciones en el archivo de salida. Los valores válidos son 512, 1024, 2048, 4096 y 8192. Estos valores están en bytes.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el `/filealign` opción para especificar la alineación de secciones en el archivo de salida. Las secciones son bloques de memoria contigua en un archivo ejecutable Portable (PE) que contiene código o datos. El `/filealign` opción permite compilar la aplicación con una alineación no estándar; la mayoría de los desarrolladores no es necesario usar esta opción.  
  
 Cada sección se alinea con un límite que es un múltiplo de la `/filealign` valor. No hay ningún valor predeterminado fijo. Si `/filealign` no se especifica, el compilador elige un valor predeterminado en tiempo de compilación.  
  
 Si especifica el tamaño de la sección, puede cambiar el tamaño del archivo de salida. Modificar el tamaño de la sección puede ser útil para los programas que se ejecuten en dispositivos más pequeños.  
  
> [!NOTE]
>  El `/filealign` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
