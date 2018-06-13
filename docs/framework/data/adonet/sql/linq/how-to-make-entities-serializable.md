---
title: 'Cómo: Serializar entidades'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: c3b877df9707e0f98dbc2238d910842649def07f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354951"
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="6f8f4-102">Cómo: Serializar entidades</span><span class="sxs-lookup"><span data-stu-id="6f8f4-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="6f8f4-103">Puede hacer que las entidades sean serializables al generar el código.</span><span class="sxs-lookup"><span data-stu-id="6f8f4-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="6f8f4-104">Las clases de entidad se decoran con el atributo <xref:System.Runtime.Serialization.DataContractAttribute> y las columnas con el atributo <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6f8f4-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="6f8f4-105">Los desarrolladores que utilizan Visual Studio pueden usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para este propósito.</span><span class="sxs-lookup"><span data-stu-id="6f8f4-105">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for this purpose.</span></span>  
  
 <span data-ttu-id="6f8f4-106">Si está utilizando la herramienta de línea de comandos SQLMetal, use la **/serialization** opción con el `unidirectional` argumento.</span><span class="sxs-lookup"><span data-stu-id="6f8f4-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="6f8f4-107">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="6f8f4-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f8f4-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f8f4-108">Example</span></span>  
 <span data-ttu-id="6f8f4-109">Con las siguientes líneas de comandos de SQLMetal se generan archivos que tienen entidades serializables.</span><span class="sxs-lookup"><span data-stu-id="6f8f4-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f8f4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f8f4-110">See Also</span></span>  
 [<span data-ttu-id="6f8f4-111">Serialización</span><span class="sxs-lookup"><span data-stu-id="6f8f4-111">Serialization</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)  
 [<span data-ttu-id="6f8f4-112">Creación del modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="6f8f4-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
