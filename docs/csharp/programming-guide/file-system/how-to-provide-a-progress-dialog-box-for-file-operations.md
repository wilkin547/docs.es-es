---
title: "Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 41da88526813e86748060bad844f13d1bf01e11f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a>Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos (Guía de programación de C#)
Puede proporcionar un cuadro de diálogo estándar en el que se muestra el progreso de las operaciones de archivos en Windows usando el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> en el espacio de nombres <xref:Microsoft.VisualBasic?displayProperty=fullName>.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a>Para agregar una referencia en Visual Studio  
  
1.  En la barra de menús, elija **Proyecto**, **Agregar referencia**.  
  
     Aparecerá el cuadro de diálogo **Administrador de referencias**.  
  
2.  En el área **Ensamblados**, elija **Framework** si no está seleccionado.  
  
3.  En la lista de nombres, seleccione la casilla **Microsoft.VisualBasic** y elija el botón **Aceptar** para cerrar el cuadro de diálogo.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código copia el directorio que especifica `sourcePath` en el directorio que especifica `destinationPath`. Este código también proporciona un cuadro de diálogo estándar en el que se muestra el tiempo estimado restante antes de que finalice la operación.  
  
 [!code-cs[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-provide-a-progress-dialog-box-for-file-operations_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Registro y sistema de archivos (Guía de programación de C#)](../../../csharp/programming-guide/file-system/index.md)
