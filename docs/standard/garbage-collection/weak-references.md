---
title: "Weak References | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "weak references, short"
  - "weak references, using"
  - "weak references, long"
  - "garbage collection, weak references"
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Weak References
El recolector de elementos no utilizados no puede recopilar un objeto en uso en una aplicación mientras el código de la aplicación pueda llegar a dicho objeto.  Se dice que la aplicación tiene una referencia segura al objeto.  
  
 Una referencia parcial permite al recolector de elementos no utilizados recopilar el objeto y, a la vez, que la aplicación tenga acceso al objeto.  Una referencia parcial sólo es válida durante un periodo de tiempo indeterminado hasta que se recopila el objeto cuando no existe ninguna referencia segura.  Al utilizar una referencia parcial, la aplicación todavía puede obtener una referencia segura al objeto, lo que evita que éste sea recopilado.  No obstante, existe siempre el riesgo de que el recolector de elementos no utilizados llegue al objeto antes de que se restablezca una referencia segura.  
  
 Las referencias parciales son útiles para los objetos que utilizan mucha memoria, pero se pueden volver a crear con facilidad si la recolección de elementos no utilizados las reclama.  
  
 Supongamos que una vista de árbol en una aplicación de Windows Forms muestra una opción jerárquica compleja de opciones al usuario.  Si los datos subyacentes son grandes, mantener el árbol en memoria es ineficaz cuando el usuario está ocupado en otra parte de la aplicación.  
  
 Cuando el usuario cambia a otro apartado de la aplicación, puede utilizar la clase <xref:System.WeakReference> para crear una referencia parcial al árbol y destruir todas las referencias seguras.  Cuando el usuario vuelve al árbol, la aplicación intenta obtener una referencia segura al árbol y, si lo logra, evita tener que reconstruir el árbol.  
  
 Para establecer una referencia parcial a un objeto, cree <xref:System.WeakReference> mediante la instancia del objeto del que va a efectuar el seguimiento.  Se establezca la propiedad de <xref:System.WeakReference.Target%2A> en ese objeto y establece la referencia original al objeto a `null`.  Para obtener un ejemplo de código, vea <xref:System.WeakReference> en la biblioteca de clases.  
  
## Referencias parciales cortas y largas  
 Puede crear una referencia parcial corta o una referencia parcial larga:  
  
-   Short  
  
     El destino de una referencia parcial corta es `null` cuando una recolección de elementos no utilizados reclama el objeto.  La referencia parcial es en sí un objeto administrado y está sujeta a la recolección de elementos no utilizados igual que cualquier otro objeto administrado.  Una referencia parcial corta es el constructor predeterminado para <xref:System.WeakReference>.  
  
-   Long  
  
     Se conserva una referencia parcial larga después de llamar al método <xref:System.Object.Finalize%2A> del objeto.  Esto permite volver a crear el objeto, pero su estado sigue siendo imprevisible.  Para utilizar una referencia larga, especifique `true` en el constructor <xref:System.WeakReference>.  
  
     Si el tipo del objeto no tiene un método <xref:System.Object.Finalize%2A>, se aplica la funcionalidad de la referencia parcial corta y la referencia parcial sólo es válida hasta que se recopile el destino, lo que se puede producir en cualquier momento una vez ejecutado el finalizador.  
  
 Para establecer una referencia segura y utilizar de nuevo el objeto, convierta la propiedad <xref:System.WeakReference.Target%2A> de <xref:System.WeakReference> en el tipo del objeto.  Si la propiedad <xref:System.WeakReference.Target%2A> devuelve `null`, se ha recopilado el objeto; si no, puede seguir utilizando el objeto porque la aplicación ha recuperado una referencia segura con él.  
  
## Instrucciones para utilizar referencias parciales  
 Utilice las referencias parciales largas sólo cuando sea necesario, ya que el estado del objeto es imprevisible después de la finalización.  
  
 Evite utilizar referencias parciales a objetos pequeños porque el propio puntero puede ser tan grande como ellos o incluso mayor.  
  
 Evite utilizar referencias parciales como solución automática para los problemas de administración de memoria.  En su lugar, desarrolle una directiva de almacenamiento en caché eficaz para controlar los objetos de la aplicación.  
  
## Vea también  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)