---
title: LINQ y directorios de archivos
ms.date: 07/20/2015
ms.assetid: 159fd5c3-3926-4071-ae78-d8e423287eb7
ms.openlocfilehash: 670611cd285a1b1f2602e2c700c2bdeb56db943f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100170"
---
# <a name="linq-and-file-directories-visual-basic"></a>LINQ y directorios de archivos (Visual Basic)

Muchas operaciones de sistema de archivos son esencialmente consultas y, por tanto, son adecuadas para el enfoque LINQ.  
  
 Tenga en cuenta que las consultas en esta sección no son destructivas. No se usan para cambiar el contenido de las carpetas o los archivos originales. Esto sigue la regla de que las consultas no deben causar efectos secundarios. En general, cualquier código (incluidas las consultas que ejecutan operadores de creación actualización y eliminación) que modifica los datos de origen se debe separar del código que solo consulta los datos.  
  
 Esta sección contiene los siguientes temas:  
  
 [Cómo: buscar archivos con un nombre o atributo especificados (Visual Basic)](how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 Muestra cómo buscar archivos examinando una o más propiedades de su objeto <xref:System.IO.FileInfo>.  
  
 [Cómo: agrupar archivos por extensión (LINQ) (Visual Basic)](how-to-group-files-by-extension-linq.md)  
 Muestra cómo devolver grupos del objeto <xref:System.IO.FileInfo> basándose en su extensión de nombre de archivo.  
  
 [Cómo: buscar el número total de bytes en un conjunto de carpetas (LINQ) (Visual Basic)](how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)  
 Muestra cómo devolver el número total de bytes en todos los archivos en un árbol de directorio especificado.  
  
 [Cómo: comparar el contenido de dos carpetas (LINQ) (Visual Basic)](how-to-compare-the-contents-of-two-folders-linq.md)s  
 Muestra cómo devolver todos los archivos que se encuentran en dos carpetas especificadas y también todos los archivos que se encuentran en una carpeta pero no en la otra.  
  
 [Cómo buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ) (Visual Basic)](how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 Muestra cómo devolver el archivo mayor o menor, o un número especificado de archivos, en un árbol de directorios.  
  
 [Cómo: consultar Archivos duplicados en un árbol de directorios (LINQ) (Visual Basic)](how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 Muestra cómo agrupar todos los nombres de archivo que aparecen en más de una ubicación en un árbol de directorio especificado. También muestra cómo realizar comparaciones más complejas basadas en un comparador personalizado.  
  
 [Cómo consultar el contenido de los archivos de una carpeta (LINQ) (Visual Basic)](how-to-query-the-contents-of-files-in-a-folder-linq.md)  
 Muestra cómo recorrer en iteración las carpetas de un árbol, abrir cada archivo y consultar el contenido del archivo.  
  
## <a name="comments"></a>Comentarios  

 Hay cierta complejidad en la creación de un origen de datos que representa de forma precisa el contenido del sistema de archivos y controla las excepciones correctamente. En los ejemplos de esta sección se crea una colección de instantáneas de objetos <xref:System.IO.FileInfo> que representa todos los archivos en una carpeta raíz especificada y todas sus subcarpetas. El estado real de cada <xref:System.IO.FileInfo> puede cambiar en el periodo comprendido entre el comienzo y el fin de la ejecución de una consulta. Por ejemplo, se puede crear una lista de objetos <xref:System.IO.FileInfo> para usarla como origen de datos. Si se intenta tener acceso a la propiedad `Length` en una consulta, el objeto <xref:System.IO.FileInfo> intentará tener acceso al sistema de archivos para actualizar el valor de `Length`. Si el archivo ya no existe, se obtendrá una excepción <xref:System.IO.FileNotFoundException> en la consulta, aunque no se esté consultando el sistema de archivos directamente. Algunas consultas de esta sección usan un método independiente que consume estas excepciones concretas en casos determinados. Otra opción consiste en mantener actualizado el origen de datos de manera dinámica mediante <xref:System.IO.FileSystemWatcher>.  
  
## <a name="see-also"></a>Vea también

- [LINQ to Objects (Visual Basic)](linq-to-objects.md)
