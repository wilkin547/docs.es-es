---
title: Filtrar para serializar entidades
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: bbe40ec448bef5f62d4182d96f82c6308639e27f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086772"
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="7bce9-102">Filtrar para serializar entidades</span><span class="sxs-lookup"><span data-stu-id="7bce9-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="7bce9-103">Puede hacer que las entidades sean serializables al generar el código.</span><span class="sxs-lookup"><span data-stu-id="7bce9-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="7bce9-104">Las clases de entidad se decoran con el atributo <xref:System.Runtime.Serialization.DataContractAttribute> y las columnas con el atributo <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7bce9-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="7bce9-105">Los desarrolladores que usan Visual Studio pueden usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para este propósito.</span><span class="sxs-lookup"><span data-stu-id="7bce9-105">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for this purpose.</span></span>  
  
 <span data-ttu-id="7bce9-106">Si usa la herramienta de línea de comandos de SQLMetal, utilice el **/serialization** opción con la `unidirectional` argumento.</span><span class="sxs-lookup"><span data-stu-id="7bce9-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="7bce9-107">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="7bce9-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bce9-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7bce9-108">Example</span></span>  
 <span data-ttu-id="7bce9-109">Con las siguientes líneas de comandos de SQLMetal se generan archivos que tienen entidades serializables.</span><span class="sxs-lookup"><span data-stu-id="7bce9-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="7bce9-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bce9-110">See also</span></span>

- [<span data-ttu-id="7bce9-111">Serialización</span><span class="sxs-lookup"><span data-stu-id="7bce9-111">Serialization</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)
- [<span data-ttu-id="7bce9-112">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="7bce9-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
