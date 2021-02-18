---
description: Mas información sobre -nowarn
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 4fb7d39aef48ff1443c342367f9e20bb37f9c5e0
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434867"
---
# <a name="-nowarn"></a>-nowarn

Suprime la capacidad del compilador para generar advertencias.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`numberList`|Opcional. Lista delimitada por comas de los números de id. de advertencia que el compilador debe suprimir. Si no se especifican los id. de advertencia, se suprimen todas las advertencias.|  
  
## <a name="remarks"></a>Comentarios  

 La opción `-nowarn` hace que el compilador no genere advertencias. Para suprimir una advertencia individual, proporcione el id. de advertencia a la opción `-nowarn` que aparece después de los dos puntos. Separe varios números de advertencia mediante comas.  
  
 Solo tendrá que especificar la parte numérica del identificador de advertencia. Por ejemplo, si quiere suprimir BC42024, la advertencia para las variables locales no utilizadas, especifique `-nowarn:42024`.  
  
 Para obtener más información sobre los números de id. de advertencia, vea [Configuración de advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Para establecer -nowarn en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Active la casilla **Deshabilitar todas las advertencias** para deshabilitar todas las advertencias.<br />     o bien<br />     Para deshabilitar una advertencia concreta, haga clic en **Ninguno** en la lista desplegable situada junto a la advertencia.|  
  
## <a name="example"></a>Ejemplo  

 El código siguiente compila `T2.vb` y no muestra ninguna advertencia.  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>Ejemplo  

 El código compila `T2.vb` siguiente y no muestra las advertencias para las variables locales no utilizadas (42024).  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
