---
title: Procedimiento para recuperar el contenido del directorio Mis documentos en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: 6d4e0bc7d300b2553d5286600cc65b7c494359b9
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56964191"
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a>Procedimiento para recuperar el contenido del directorio Mis documentos en Visual Basic
El objeto <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> se puede usar para leer en muchos de los directorios de **Todos los usuarios**, como **Mis documentos** o **Escritorio**.  
  
### <a name="to-read-from-the-my-documents-folder"></a>Para leer de la carpeta Mis documentos  
  
-   Use el método `ReadAllText` para leer el texto de cada archivo situado en un directorio concreto. El código siguiente especifica un directorio y un archivo y, después, usa `ReadAllText` para leerlos en la cadena denominada `patients`.  
  
     [!code-vb[VbVbcnMyFileSystem#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
