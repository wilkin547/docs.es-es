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
ms.openlocfilehash: 2893c1760a856a7d736e9c03ba33d9771722b5b2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929470"
---
# <a name="-filealign"></a>-filealign
Especifica dónde se alinean las secciones del archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a>Argumentos  
 `number`  
 Necesario. Valor que especifica la alineación de las secciones del archivo de salida. Los valores válidos son 512, 1024, 2048, 4096 y 8192. Estos valores están en bytes.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar la `-filealign` opción para especificar la alineación de las secciones en el archivo de salida. Las secciones son bloques de memoria contigua en un archivo portable ejecutable (PE) que contiene código o datos. La `-filealign` opción le permite compilar la aplicación con una alineación no estándar; la mayoría de los desarrolladores no necesitan usar esta opción.  
  
 Cada sección se alinea en un límite que es un múltiplo del `-filealign` valor. No hay ningún valor predeterminado fijo. Si `-filealign` no se especifica, el compilador elige un valor predeterminado en tiempo de compilación.  
  
 Al especificar el tamaño de la sección, puede cambiar el tamaño del archivo de salida. Modificar el tamaño de la sección puede ser útil para los programas que se ejecutan en dispositivos más pequeños.  
  
> [!NOTE]
> La `-filealign` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
