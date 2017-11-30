---
title: /filealign
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dbabc19c85501b97ef5443a6f6e12524f8de7d91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
 Puede usar el `/filealign` opción para especificar la alineación de secciones en el archivo de salida. Las secciones son bloques de memoria contigua en un archivo ejecutable Portable (PE) que contiene código o datos. El `/filealign` opción le permite compilar su aplicación con una alineación no estándar; la mayoría de los desarrolladores no es necesario usar esta opción.  
  
 Cada sección se alinea en un límite que es un múltiplo de la `/filealign` valor. No hay ningún valor predeterminado fijo. Si `/filealign` no se especifica, el compilador elige un valor predeterminado en tiempo de compilación.  
  
 Al especificar el tamaño de la sección, puede cambiar el tamaño del archivo de salida. Modificar el tamaño de la sección puede ser útil para los programas que se ejecutan en dispositivos más pequeños.  
  
> [!NOTE]
>  El `/filealign` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
