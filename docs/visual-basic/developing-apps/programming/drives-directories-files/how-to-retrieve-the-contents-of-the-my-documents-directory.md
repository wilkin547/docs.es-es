---
title: 'Cómo: Recuperar el contenido del directorio Mis documentos en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: 1d0536c65949dab7d431f3a4cb7b3293bddb7008
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a>Cómo: Recuperar el contenido del directorio Mis documentos en Visual Basic
El objeto <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> se puede usar para leer en muchos de los directorios de **Todos los usuarios**, como **Mis documentos** o **Escritorio**.  
  
### <a name="to-read-from-the-my-documents-folder"></a>Para leer de la carpeta Mis documentos  
  
-   Use el método `ReadAllText` para leer el texto de cada archivo situado en un directorio concreto. El código siguiente especifica un directorio y un archivo y, después, usa `ReadAllText` para leerlos en la cadena denominada `patients`.  
  
     [!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
