---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: e18fe451ea4a80ac959ed61b66394920f8bf177f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336088"
---
# <a name="-optionstrict"></a>-optionstrict
Exige la semántica estricta de tipos para restringir las conversiones implícitas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Opcional. El `-optionstrict+` opción restringe la conversión de tipos implícita. El valor predeterminado para esta opción es `-optionstrict-`. El `-optionstrict+` opción es igual a `-optionstrict`. Puede usar tanto para la semántica de tipos permisiva.  
  
 `custom`  
 Obligatorio. Advertir cuando no se respete la semántica estricta del lenguaje.  
  
## <a name="remarks"></a>Comentarios  
 Cuando `-optionstrict+` está en vigor, se pueden realizar solo las conversiones de tipo de ampliación implícitamente. Conversiones de tipos, como la asignación de restricción implícitas un `Decimal` tipo object para un objeto de tipo entero, se notifican como errores.  
  
 Para generar advertencias para las conversiones de tipo de restricción implícitas, use `-optionstrict:custom`. Use `-nowarn:numberlist` para ignorar las advertencias determinadas y `-warnaserror:numberlist` para tratar determinadas advertencias como errores.  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a>Para establecer - optionstrict en el IDE de Visual Studio  
  
1. Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades.**   
  
2. Haga clic en la pestaña **Compilar**.  
  
3. Modifique el valor en el **Option Strict** cuadro.  
  
### <a name="to-set--optionstrict-programmatically"></a>Para establecer mediante programación - optionstrict  
  
-   Consulte [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `Test.vb` utilizando la semántica estricta de tipos.  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [-warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
