---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 91f2a27ed9b6fb296dbb9e50fc488fd012311890
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005509"
---
# <a name="-main"></a>-main
Especifica la clase o el módulo que contiene el procedimiento `Sub Main`.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a>Argumentos  
 `location`  
 Obligatorio. Nombre de la clase o módulo que contiene el `Sub Main` procedimiento al que se va a llamar cuando se inicie el programa. Puede tener el formato **-Main: module** o **-Main: Namespace. Module**.  
  
## <a name="remarks"></a>Comentarios  
 Utilice esta opción cuando cree un archivo ejecutable o un programa ejecutable de Windows. Si se omite la opción **-Main** , el compilador busca una `Sub Main` compartida válida en todas las clases y módulos públicos.  
  
 Vea el [procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) para obtener una explicación de las distintas formas del procedimiento de `Main`.  
  
 Cuando `location` es una clase que hereda de <xref:System.Windows.Forms.Form>, el compilador proporciona un procedimiento de `Main` predeterminado que inicia la aplicación si la clase no tiene `Main` procedimiento. Esto le permite compilar código en la línea de comandos que se creó en el entorno de desarrollo.  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a>Para establecer-Main en el entorno de desarrollo integrado de Visual Studio  
  
1. Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.  
  
2. Haga clic en la pestaña **Aplicación** .  
  
3. Asegúrese de que la casilla **Habilitar marco de aplicación** no esté activada.  
  
4. Modifique el valor en el cuadro **objeto de inicio** .  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se compilan `T2.vb` y `T3.vb`, especificando que el procedimiento `Sub Main` se encontrará en la clase `Test2`.  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
