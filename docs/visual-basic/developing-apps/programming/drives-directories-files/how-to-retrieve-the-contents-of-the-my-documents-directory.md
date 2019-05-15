---
title: Procedimiento para recuperar el contenido del directorio Mis documentos en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: f03dbe1811dd5367dab2d32d94ba35ff05fad198
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623147"
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a>Procedimiento para recuperar el contenido del directorio Mis documentos en Visual Basic
El objeto <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> se puede usar para leer en muchos de los directorios de **Todos los usuarios**, como **Mis documentos** o **Escritorio**.  
  
### <a name="to-read-from-the-my-documents-folder"></a>Para leer de la carpeta Mis documentos  
  
- Use el método `ReadAllText` para leer el texto de cada archivo situado en un directorio concreto. El código siguiente especifica un directorio y un archivo y, después, usa `ReadAllText` para leerlos en la cadena denominada `patients`.  
  
     [!code-vb[VbVbcnMyFileSystem#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
