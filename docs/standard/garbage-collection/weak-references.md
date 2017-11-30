---
title: Referencias parciales
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak references, short
- weak references, using
- weak references, long
- garbage collection, weak references
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 906c23caa7065486bb094ad2475ed9e7e24b3d9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="weak-references"></a>Referencias parciales
El recolector de elementos no utilizados no puede recopilar un objeto que está siendo usado por una aplicación mientras el código de aplicación pueda llegar a ese objeto. En este caso, se dice que la aplicación tiene una referencia segura al objeto.  
  
 Una referencia débil permite que el recolector de elementos no utilizados recopile el objeto mientras sigue permitiendo que la aplicación tenga acceso al objeto. Una referencia débil es válida solo durante un período indeterminado de tiempo, hasta que el objeto se recopila cuando no existe ninguna referencia segura. Cuando se usa una referencia débil, la aplicación todavía puede obtener una referencia segura al objeto, lo que evita que se recopile. Pero, siempre existe el riesgo de que el recolector de elementos no utilizados llegue al objeto antes de que se restablezca una referencia segura.  
  
 Las referencias débiles son útiles para objetos que usan mucha memoria, pero que pueden volverse a crear fácilmente si los reclama la recolección de elementos no utilizados.  
  
 Imagine que una vista de árbol en una aplicación de formularios Windows Forms muestra una elección jerárquica compleja de opciones al usuario. Si la cantidad de datos subyacentes es grande, mantener el árbol en memoria es ineficaz cuando el usuario está ocupado en otra parte de la aplicación.  
  
 Cuando el usuario cambia a otra parte de la aplicación, puede usar el <xref:System.WeakReference> clase para crear una referencia débil al árbol y destruir todas las referencias seguras. Cuando el usuario vuelve al árbol, la aplicación intenta obtener una referencia segura al árbol y, si la obtiene, evita tener que reconstruir el árbol.  
  
 Para establecer una referencia débil a un objeto, se crea un <xref:System.WeakReference> utilizando la instancia del objeto para realizar su seguimiento. A continuación, establezca el <xref:System.WeakReference.Target%2A> propiedad en ese objeto y el conjunto original hacen referencia al objeto para `null`. Para obtener un ejemplo de código, consulte <xref:System.WeakReference> en la biblioteca de clases.  
  
## <a name="short-and-long-weak-references"></a>Referencias débiles cortas y largas  
 Puede crear una referencia débil corta o una referencia débil larga:  
  
-   Short  
  
     El destino de una referencia débil corta se convierte en `null` cuando el objeto es reclamado por la recolección de elementos no utilizados. La referencia débil es, en sí, un objeto administrado y está sujeta a la recolección de elementos no utilizados igual que cualquier otro objeto administrado.  Una referencia débil corta es el constructor predeterminado para <xref:System.WeakReference>.  
  
-   Long  
  
     Se conserva una referencia débil larga después del objeto <xref:System.Object.Finalize%2A> ha llamado al método. Esto permite que el objeto se vuelva a crear, pero el estado del objeto sigue siendo imprevisible. Para utilizar una referencia larga, especifique `true` en el <xref:System.WeakReference> constructor.  
  
     Si el tipo del objeto no tiene un <xref:System.Object.Finalize%2A> la funcionalidad de la referencia débil corta de método, se aplica y la referencia débil es válida solo hasta que se recopile el destino, lo que puede producirse en cualquier momento después el finalizador se ejecute.  
  
 Para establecer una referencia segura y vuelve a utilizar el objeto, convierte el <xref:System.WeakReference.Target%2A> propiedad de un <xref:System.WeakReference> para el tipo del objeto. Si el <xref:System.WeakReference.Target%2A> propiedad devuelve `null`, el objeto se ha recopilado; en caso contrario, aún puede usar el objeto porque la aplicación ha recuperado una referencia segura a él.  
  
## <a name="guidelines-for-using-weak-references"></a>Directrices para usar referencias débiles  
 Use referencias débiles largas solo cuando sea necesario, ya que el estado del objeto es imprevisible después de la finalización.  
  
 Evite usar referencias débiles a objetos pequeños porque el propio puntero puede ser igual de grande o mayor.  
  
 Evite usar referencias débiles como solución automática para problemas de administración de memoria. En su lugar, desarrolle una directiva eficaz de almacenamiento en caché para controlar los objetos de la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Recolección de elementos no utilizados](../../../docs/standard/garbage-collection/index.md)
