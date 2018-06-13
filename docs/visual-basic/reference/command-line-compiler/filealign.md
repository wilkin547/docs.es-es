---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9c854060e5254cedc6c1004ac3e4f25fbdbbd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650672"
---
# <a name="-filealign"></a>-filealign
Especifica dónde se alinean las secciones del archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a>Argumentos  
 `number`  
 Requerido. Un valor que especifica la alineación de secciones en el archivo de salida. Los valores válidos son 512, 1024, 2048, 4096 y 8192. Estos valores están en bytes.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el `-filealign` opción para especificar la alineación de secciones en el archivo de salida. Las secciones son bloques de memoria contigua en un archivo ejecutable Portable (PE) que contiene código o datos. El `-filealign` opción le permite compilar su aplicación con una alineación no estándar; la mayoría de los desarrolladores no es necesario usar esta opción.  
  
 Cada sección se alinea en un límite que es un múltiplo de la `-filealign` valor. No hay ningún valor predeterminado fijo. Si `-filealign` no se especifica, el compilador elige un valor predeterminado en tiempo de compilación.  
  
 Al especificar el tamaño de la sección, puede cambiar el tamaño del archivo de salida. Modificar el tamaño de la sección puede ser útil para los programas que se ejecutan en dispositivos más pequeños.  
  
> [!NOTE]
>  El `-filealign` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
