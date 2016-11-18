---
title: Referencias parciales
description: Referencias parciales
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/19/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 22319f2f-0008-4ace-815e-545892a0512a
translationtype: Human Translation
ms.sourcegitcommit: 213ce098bcc2b5e31c55e759d895254d5ca33caa
ms.openlocfilehash: a966f430c00f07d48f2210d64f03d6805f4e3097

---

# <a name="weak-references"></a>Referencias parciales

El recolector de elementos no utilizados no puede recopilar un objeto que está siendo usado por una aplicación mientras el código de aplicación pueda llegar a ese objeto. En este caso, se dice que la aplicación tiene una referencia segura al objeto. 

Una referencia débil permite que el recolector de elementos no utilizados recopile el objeto mientras sigue permitiendo que la aplicación tenga acceso al objeto. Una referencia débil es válida solo durante un período indeterminado de tiempo, hasta que el objeto se recopila cuando no existe ninguna referencia segura. Cuando se usa una referencia débil, la aplicación todavía puede obtener una referencia segura al objeto, lo que evita que se recopile. Pero, siempre existe el riesgo de que el recolector de elementos no utilizados llegue al objeto antes de que se restablezca una referencia segura.

Las referencias débiles son útiles para objetos que usan mucha memoria, pero que pueden volverse a crear fácilmente si los reclama la recolección de elementos no utilizados. 

Imagine una vista de árbol que muestra una jerarquía compleja de opciones al usuario. Si la cantidad de datos subyacentes es grande, mantener el árbol en memoria es ineficaz cuando el usuario está ocupado en otra parte de la aplicación. 

Cuando el usuario cambia a otra parte de la aplicación, se pueden usar las clases [WeakReference](xref:System.WeakReference) o [WeakReference&lt;T&gt;](xref:System.WeakReference%601) para crear una referencia débil al árbol y destruir todas las referencias seguras. Cuando el usuario vuelve al árbol, la aplicación intenta obtener una referencia segura al árbol y, si la obtiene, evita tener que reconstruir el árbol.

Para establecer una referencia débil a un objeto, se crea un elemento [WeakReference](xref:System.WeakReference) usando la instancia del objeto que se debe seguir. Después, se establece la propiedad [Target](xref:System.WeakReference.Target) como ese objeto y se establece la referencia original al objeto como null. 

## <a name="short-and-long-weak-references"></a>Referencias débiles cortas y largas

Puede crear una referencia débil corta o una referencia débil larga: 

* Short

  El destino de una referencia débil corta se convierte en `null` cuando el objeto es reclamado por la recolección de elementos no utilizados. La referencia débil es, en sí, un objeto administrado y está sujeta a la recolección de elementos no utilizados igual que cualquier otro objeto administrado. Una referencia débil corta es el constructor predeterminado para [WeakReference](xref:System.WeakReference). 

* Long

  Una referencia débil larga se conserva después de que se llame al método [Finalize](xref:System.Object.Finalize) del objeto. Esto permite que el objeto se vuelva a crear, pero el estado del objeto sigue siendo imprevisible. Para usar una referencia larga, especifique `true` en el constructor [WeakReference](xref:System.WeakReference). 

  Si el tipo de objeto no tiene un método [Finalize](xref:System.Object.Finalize), se aplica la funcionalidad de referencia débil corta y la referencia débil es válida solo hasta que se recopile el destino, lo que puede ocurrir en cualquier momento después de que se ejecute el finalizador.

Para establecer una referencia segura y usar el objeto de nuevo, convierta la propiedad [Target](xref:System.WeakReference.Target) de [WeakReference](xref:System.WeakReference) en el tipo del objeto. Si la propiedad [Target](xref:System.WeakReference.Target) devuelve `null`, el objeto se ha recopilado; en caso contrario, aún puede usar el objeto, porque la aplicación ha obtenido una referencia segura a este.

## <a name="guidelines-for-using-weak-references"></a>Directrices para usar referencias débiles

Use referencias débiles largas solo cuando sea necesario, ya que el estado del objeto es imprevisible después de la finalización. 

Evite usar referencias débiles a objetos pequeños porque el propio puntero puede ser igual de grande o mayor. 

Evite usar referencias débiles como solución automática para problemas de administración de memoria. En su lugar, desarrolle una directiva eficaz de almacenamiento en caché para controlar los objetos de la aplicación. 

## <a name="see-also"></a>Vea también

[Recolección de elementos no utilizados en .NET](index.md)



<!--HONumber=Nov16_HO3-->


