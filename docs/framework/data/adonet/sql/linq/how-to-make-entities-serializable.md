---
title: "Cómo: Serializar entidades"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 96d8e05fd6ce71536eacd909a831da0e14aa2f3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="238be-102">Cómo: Serializar entidades</span><span class="sxs-lookup"><span data-stu-id="238be-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="238be-103">Puede hacer que las entidades sean serializables al generar el código.</span><span class="sxs-lookup"><span data-stu-id="238be-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="238be-104">Las clases de entidad se decoran con el atributo <xref:System.Runtime.Serialization.DataContractAttribute> y las columnas con el atributo <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="238be-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="238be-105">Los desarrolladores que utilizan [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] pueden usar [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para este propósito.</span><span class="sxs-lookup"><span data-stu-id="238be-105">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for this purpose.</span></span>  
  
 <span data-ttu-id="238be-106">Si está utilizando la herramienta de línea de comandos SQLMetal, use la **/serialization** opción con el `unidirectional` argumento.</span><span class="sxs-lookup"><span data-stu-id="238be-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="238be-107">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="238be-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="238be-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="238be-108">Example</span></span>  
 <span data-ttu-id="238be-109">Con las siguientes líneas de comandos de SQLMetal se generan archivos que tienen entidades serializables.</span><span class="sxs-lookup"><span data-stu-id="238be-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="238be-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="238be-110">See Also</span></span>  
 [<span data-ttu-id="238be-111">Serialización</span><span class="sxs-lookup"><span data-stu-id="238be-111">Serialization</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)  
 [<span data-ttu-id="238be-112">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="238be-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
