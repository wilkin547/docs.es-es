---
description: Más información sobre -filealign
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
ms.openlocfilehash: f32ae370c0ef832b501f085351eadb9b6156c730
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100470296"
---
# <a name="-filealign"></a>-filealign

Especifica dónde se alinean las secciones del archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a>Argumentos  

 `number`  
 Obligatorio. Un valor que especifica la alineación de las secciones del archivo de salida. Los valores válidos son 512, 1024, 2048, 4096 y 8192. Estos valores están en bytes.  
  
## <a name="remarks"></a>Comentarios  

 Puede usar la opción `-filealign` para especificar la alineación de las secciones en el archivo de salida. Las secciones son bloques de memoria contigua en un archivo portable ejecutable (PE) que contiene código o datos. La opción `-filealign` permite compilar la aplicación con una alineación no estándar; la mayoría de los desarrolladores no necesitan usar esta opción.  
  
 Cada sección se alinea en un límite que es un múltiplo del valor `-filealign`. No hay ningún valor predeterminado fijo. Si no se especifica `-filealign`, el compilador elige un valor predeterminado en tiempo de compilación.  
  
 Al especificar el tamaño de la sección, puede cambiar el tamaño del archivo de salida. Modificar el tamaño de la sección puede ser útil para los programas que se ejecutan en dispositivos más pequeños.  
  
> [!NOTE]
> La opción `-filealign` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
