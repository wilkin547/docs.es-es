---
description: Más información sobre -verbose
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: ea222d4f284bcaf163b142269fe250a081b0ee4f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100470141"
---
# <a name="-verbose"></a>-verbose

Hace que el compilador genere mensajes de estado y de error detallados.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  

 `+` &#124; `-`  
 Opcional. Especificar `-verbose` equivale a especificar `-verbose+`, lo que hace que el compilador emita mensajes detallados. El valor predeterminado de esta opción es `-verbose-`.  
  
## <a name="remarks"></a>Comentarios  

 La opción `-verbose` muestra información sobre el número total de errores emitidos por el compilador, notifica qué ensamblados carga un módulo y muestra los archivos que se están compilando actualmente.  
  
> [!NOTE]
> La opción `-verbose` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  

 En el código siguiente se compila `In.vb` y se indica al compilador que muestre información de estado detallada.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
