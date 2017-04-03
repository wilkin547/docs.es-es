---
title: "Cómo: Compartir un ensamblado con otras aplicaciones (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 79397b18b67becf91d04358ea62cb2351be7d252
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a>Cómo: Compartir un ensamblado con otras aplicaciones (C#)
Los ensamblados pueden ser privados o compartidos: de forma predeterminada, la mayoría de los programas sencillos constan de un ensamblado privado porque no se diseñaron para ser usados por otras aplicaciones.  
  
 Para compartir un ensamblado con otras aplicaciones, debe colocarse en la [caché global de ensamblados](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202) (GAC).  
  
### <a name="sharing-an-assembly"></a>Compartir un ensamblado  
  
1.  Cree el ensamblado. Para obtener más información, vea [Creating Assemblies](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4) (Crear ensamblados).  
  
2.  Asigne un nombre seguro al ensamblado. Para obtener más información, vea [Cómo: Firmar un ensamblado con un nombre seguro](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67).  
  
3.  Asigne la información de versión al ensamblado. Para obtener más información, vea [Versiones de los ensamblados](https://msdn.microsoft.com/library/51ket42z).  
  
4.  Agregue el ensamblado a la caché global de ensamblados. Para obtener más información, vea [Cómo: Instalar un ensamblado en la memoria caché global de ensamblados](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743).  
  
5.  Obtenga acceso a los tipos contenidos en el ensamblado desde las otras aplicaciones. Para obtener más información, vea [Cómo: Hacer referencia a un ensamblado con nombre seguro](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../../csharp/programming-guide/index.md)   
 [Programar con ensamblados](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)
