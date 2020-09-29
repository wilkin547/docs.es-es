---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: fb317b3c555d151e132122c476ce19bdeceb1321
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065624"
---
# <a name="-main"></a>-main

Especifica la clase o el módulo que contiene el procedimiento `Sub Main`.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a>Argumentos  

 `location`  
 Obligatorio. Nombre de la clase o módulo que contiene el procedimiento `Sub Main` al que se va a llamar cuando el programa se inicia. Puede tener el formato **-main:module** o **-main:namespace.module**.  
  
## <a name="remarks"></a>Comentarios  

 Use esta opción al crear un archivo ejecutable o un programa ejecutable de Windows. Si la opción **-main** se omite, el compilador busca un elemento `Sub Main` compartido válido en todas las clases y módulos públicos.  
  
 Vea [Procedimiento Main en Visual Basic](../../programming-guide/program-structure/main-procedure.md) para obtener una explicación de los distintos formatos del procedimiento `Main`.  
  
 Cuando `location` es una clase que hereda de <xref:System.Windows.Forms.Form>, el compilador proporciona un procedimiento `Main` predeterminado que inicia la aplicación si la clase no tiene un procedimiento `Main`. Esto permite compilar código en la línea de comandos que se creó en el entorno de desarrollo.  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a>Para definir -main en el entorno de desarrollo integrado de Visual Studio  
  
1. Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.  
  
2. Haga clic en la pestaña **Aplicación** .  
  
3. Asegúrese de que la casilla **Habilitar marco de trabajo de la aplicación** está desactivada.  
  
4. Modifique el valor del cuadro **Objeto de inicio**.  
  
## <a name="example"></a>Ejemplo  

 En el siguiente código se compilan `T2.vb` y `T3.vb`, especificando que el procedimiento `Sub Main` va a estar en la clase `Test2`.  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-target (Visual Basic)](target.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [Procedimiento Main en Visual Basic](../../programming-guide/program-structure/main-procedure.md)
