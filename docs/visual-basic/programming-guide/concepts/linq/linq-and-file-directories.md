---
title: LINQ y directorios de archivos (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 159fd5c3-3926-4071-ae78-d8e423287eb7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5536ae95b42cdaddda2c4cae97a114681e94b0ab
ms.lasthandoff: 03/13/2017

---
# <a name="linq-and-file-directories-visual-basic"></a>LINQ y directorios de archivos (Visual Basic)
Muchas operaciones de sistema de archivos son esencialmente consultas y, por tanto, son adecuadas para el enfoque LINQ.  
  
 Tenga en cuenta que las consultas en esta sección no destructiva. No se utilizan para cambiar el contenido de las carpetas o los archivos originales. Sigue la regla de que las consultas no deberían causar efectos secundarios. En general, cualquier código (incluidas las consultas que realizan crean, actualización y eliminación operadores) que modifica los datos de origen se deben separar el código que sólo consulta los datos.  
  
 Esta sección contiene los siguientes temas:  
  
 [Cómo: buscar archivos con un atributo especificado o un nombre (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 Muestra cómo buscar archivos examinando una o más propiedades de su <xref:System.IO.FileInfo>objeto.</xref:System.IO.FileInfo>  
  
 [Cómo: agrupar archivos por extensión (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 Muestra cómo devolver grupos de <xref:System.IO.FileInfo>objeto basado en su extensión de nombre de archivo.</xref:System.IO.FileInfo>  
  
 [Cómo: buscar el número Total de Bytes en un conjunto de carpetas (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)  
 Muestra cómo devolver el número total de bytes en todos los archivos en un árbol de directorio especificado.  
  
 [Cómo: comparar el contenido de dos carpetas (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s  
 Muestra cómo devolver todos los archivos que se encuentran en dos carpetas especificadas y también todos los archivos que se encuentran en una carpeta pero no el otro.  
  
 [Cómo: buscar el mayor tamaño o archivos en un árbol de directorios (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 Muestra cómo devolver el archivo mayor o menor, o un número especificado de archivos, en un árbol de directorios.  
  
 [Cómo: buscar archivos duplicados en un árbol de directorios (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 Muestra cómo agrupar todos los nombres de archivo que se producen en más de una ubicación en un árbol de directorio especificado. También muestra cómo realizar comparaciones más complejas basadas en un comparador personalizado.  
  
 [Cómo: consultar el contenido de archivos en una carpeta (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-the-contents-of-files-in-a-folder-linq.md)  
 Muestra cómo recorrer en iteración las carpetas de un árbol, abra cada archivo y consultar el contenido del archivo.  
  
## <a name="comments"></a>Comentarios  
 Hay cierta complejidad implicada en la creación de un origen de datos que representa el contenido del sistema de archivos de forma precisa y controla las excepciones correctamente. Los ejemplos de esta sección crean una colección de instantáneas <xref:System.IO.FileInfo>objetos que representa todos los archivos en una carpeta raíz especificada y todas sus subcarpetas.</xref:System.IO.FileInfo> El estado real de cada <xref:System.IO.FileInfo>puede cambiar entre las fechas de comienzo y fin de ejecutar una consulta.</xref:System.IO.FileInfo> Por ejemplo, puede crear una lista de <xref:System.IO.FileInfo>objetos que se va a usar como origen de datos.</xref:System.IO.FileInfo> Si intenta tener acceso a la `Length` propiedad en una consulta, el <xref:System.IO.FileInfo>objeto intentará tener acceso al sistema de archivos para actualizar el valor de `Length`.</xref:System.IO.FileInfo> Si el archivo ya no existe, obtendrá un <xref:System.IO.FileNotFoundException>en la consulta, aunque no esté consultando el sistema de archivos directamente.</xref:System.IO.FileNotFoundException> Algunas consultas de esta sección usan un método independiente que utiliza estas excepciones concretas en algunos casos. Otra opción consiste en mantener el origen de datos que se actualiza dinámicamente mediante el <xref:System.IO.FileSystemWatcher>.</xref:System.IO.FileSystemWatcher>  
  
## <a name="see-also"></a>Vea también  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
