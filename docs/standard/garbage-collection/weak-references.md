---
title: Referencias parciales
description: Descubra las referencias débiles, que permiten que el recolector de elementos no utilizados de .NET recopile un objeto al tiempo que permite que la aplicación acceda al objeto.
ms.date: 03/30/2017
helpviewer_keywords:
- weak references, short
- weak references, using
- weak references, long
- garbage collection, weak references
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
ms.openlocfilehash: 1eb5e57f5cc1065f1b8510e4fb0a980a85abca29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714216"
---
# <a name="weak-references"></a>Referencias parciales

El recolector de elementos no utilizados no puede recopilar un objeto que está siendo usado por una aplicación mientras el código de aplicación pueda llegar a ese objeto. En este caso, se dice que la aplicación tiene una referencia segura al objeto.  
  
 Una referencia débil permite que el recolector de elementos no utilizados recopile el objeto mientras sigue permitiendo que la aplicación tenga acceso al objeto. Una referencia débil es válida solo durante un período indeterminado de tiempo, hasta que el objeto se recopila cuando no existe ninguna referencia segura. Cuando se usa una referencia débil, la aplicación todavía puede obtener una referencia segura al objeto, lo que evita que se recopile. Pero, siempre existe el riesgo de que el recolector de elementos no utilizados llegue al objeto antes de que se restablezca una referencia segura.  
  
 Las referencias débiles son útiles para objetos que usan mucha memoria, pero que pueden volverse a crear fácilmente si los reclama la recolección de elementos no utilizados.  
  
 Imagine una vista de árbol de una aplicación de Windows Forms que muestra una jerarquía compleja de opciones al usuario. Si la cantidad de datos subyacentes es grande, mantener el árbol en memoria es ineficaz cuando el usuario está ocupado en otra parte de la aplicación.  
  
 Cuando el usuario cambia a otra parte de la aplicación, se puede usar la clase <xref:System.WeakReference> para crear una referencia débil al árbol y destruir todas las referencias seguras. Cuando el usuario vuelve al árbol, la aplicación intenta obtener una referencia segura al árbol y, si la obtiene, evita tener que reconstruir el árbol.  
  
 Para establecer una referencia débil a un objeto, se crea un elemento <xref:System.WeakReference> usando la instancia del objeto que se debe seguir. Después, se establece la propiedad <xref:System.WeakReference.Target%2A> como ese objeto y se establece la referencia original al objeto como `null`. Para obtener un ejemplo de código, consulte <xref:System.WeakReference> en la biblioteca de clases.  
  
## <a name="short-and-long-weak-references"></a>Referencias débiles cortas y largas  

 Puede crear una referencia débil corta o una referencia débil larga:  
  
- Short  
  
     El destino de una referencia débil corta se convierte en `null` cuando el objeto es reclamado por la recolección de elementos no utilizados. La referencia débil es, en sí, un objeto administrado y está sujeta a la recolección de elementos no utilizados igual que cualquier otro objeto administrado.  Una referencia débil corta es el constructor sin parámetros para <xref:System.WeakReference>.  
  
- Long  
  
     Una referencia débil larga se conserva después de que se llame al método <xref:System.Object.Finalize%2A> del objeto. Esto permite que el objeto se vuelva a crear, pero el estado del objeto sigue siendo imprevisible. Para usar una referencia larga, especifique `true` en el constructor <xref:System.WeakReference>.  
  
     Si el tipo de objeto no tiene un método <xref:System.Object.Finalize%2A>, se aplica la funcionalidad de referencia débil corta y la referencia débil es válida solo hasta que se recopile el destino, lo que puede ocurrir en cualquier momento después de que se ejecute el finalizador.  
  
 Para establecer una referencia segura y usar el objeto de nuevo, convierta la propiedad <xref:System.WeakReference.Target%2A> de <xref:System.WeakReference> en el tipo del objeto. Si la propiedad <xref:System.WeakReference.Target%2A> devuelve `null`, el objeto se ha recopilado; en caso contrario, aún puede usar el objeto, porque la aplicación ha obtenido una referencia segura a este.  
  
## <a name="guidelines-for-using-weak-references"></a>Directrices para usar referencias débiles  

 Use referencias débiles largas solo cuando sea necesario, ya que el estado del objeto es imprevisible después de la finalización.  
  
 Evite usar referencias débiles a objetos pequeños porque el propio puntero puede ser igual de grande o mayor.  
  
 Evite usar referencias débiles como solución automática para problemas de administración de memoria. En su lugar, desarrolle una directiva eficaz de almacenamiento en caché para controlar los objetos de la aplicación.  
  
## <a name="see-also"></a>Vea también

- [Recolección de elementos no utilizados](index.md)
