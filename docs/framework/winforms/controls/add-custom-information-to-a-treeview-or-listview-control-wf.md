---
title: 'Cómo: Agregar información personalizada a un Control TreeView o ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- ListItem
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- examples [Windows Forms], ListView control
- ListView control [Windows Forms], adding custom information
- TreeView control [Windows Forms], adding custom information
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
ms.openlocfilehash: faed586a5814526b0169ea46c8bb452e3777d8ba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182432"
---
# <a name="how-to-add-custom-information-to-a-treeview-or-listview-control-windows-forms"></a><span data-ttu-id="87ff2-102">Cómo: Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="87ff2-102">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>
<span data-ttu-id="87ff2-103">Puede crear un nodo derivado en <xref:System.Windows.Forms.TreeView> un control de formularios <xref:System.Windows.Forms.ListView> Windows Forms o un elemento derivado en un control.</span><span class="sxs-lookup"><span data-stu-id="87ff2-103">You can create a derived node in a Windows Forms <xref:System.Windows.Forms.TreeView> control or a derived item in a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="87ff2-104">La derivación permite agregar cualquier campo que se necesite, así como métodos personalizados y constructores para controlarlos.</span><span class="sxs-lookup"><span data-stu-id="87ff2-104">Derivation allows you to add any fields you require, as well as custom methods and constructors for handling them.</span></span> <span data-ttu-id="87ff2-105">Uno de los usos de esta característica consiste en adjuntar un objeto Customer a cada nodo de árbol o elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="87ff2-105">One use of this feature is to attach a Customer object to each tree node or list item.</span></span> <span data-ttu-id="87ff2-106">Los ejemplos aquí <xref:System.Windows.Forms.TreeView> son para un control, pero <xref:System.Windows.Forms.ListView> se puede usar el mismo enfoque para un control.</span><span class="sxs-lookup"><span data-stu-id="87ff2-106">The examples here are for a <xref:System.Windows.Forms.TreeView> control, but the same approach can be used for a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
### <a name="to-derive-a-tree-node"></a><span data-ttu-id="87ff2-107">Para derivar un nodo de árbol</span><span class="sxs-lookup"><span data-stu-id="87ff2-107">To derive a tree node</span></span>  
  
- <span data-ttu-id="87ff2-108">Cree una nueva clase de nodo, derivada de la <xref:System.Windows.Forms.TreeNode> clase, que tiene un campo personalizado para registrar una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="87ff2-108">Create a new node class, derived from the <xref:System.Windows.Forms.TreeNode> class, which has a custom field to record a file path.</span></span>  
  
    ```vb  
    Class myTreeNode  
       Inherits TreeNode  
  
       Public FilePath As String  
  
       Sub New(ByVal fp As String)  
          MyBase.New()  
          FilePath = fp  
          Me.Text = fp.Substring(fp.LastIndexOf("\"))  
       End Sub  
    End Class  
    ```  
  
    ```csharp  
    class myTreeNode : TreeNode  
    {  
       public string FilePath;  
  
       public myTreeNode(string fp)  
       {  
          FilePath = fp;  
          this.Text = fp.Substring(fp.LastIndexOf("\\"));  
       }  
    }  
    ```  
  
    ```cpp  
    ref class myTreeNode : public TreeNode  
    {  
    public:  
       System::String ^ FilePath;  
  
       myTreeNode(System::String ^ fp)  
       {  
          FilePath = fp;  
          this->Text = fp->Substring(fp->LastIndexOf("\\"));  
       }  
    };  
    ```  
  
### <a name="to-use-a-derived-tree-node"></a><span data-ttu-id="87ff2-109">Para utilizar un nodo de árbol derivado</span><span class="sxs-lookup"><span data-stu-id="87ff2-109">To use a derived tree node</span></span>  
  
1. <span data-ttu-id="87ff2-110">Puede utilizar el nuevo nodo de árbol derivado como parámetro para llamadas de función.</span><span class="sxs-lookup"><span data-stu-id="87ff2-110">You can use the new derived tree node as a parameter to function calls.</span></span>  
  
     <span data-ttu-id="87ff2-111">En el ejemplo siguiente, la ruta de acceso establecida para la ubicación del archivo de texto es la carpeta Mis documentos.</span><span class="sxs-lookup"><span data-stu-id="87ff2-111">In the example below, the path set for the location of the text file is the My Documents folder.</span></span> <span data-ttu-id="87ff2-112">Se utiliza esta ubicación porque se puede suponer que la mayoría de los equipos que ejecuten el sistema operativo Windows tendrán este directorio.</span><span class="sxs-lookup"><span data-stu-id="87ff2-112">This is done because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="87ff2-113">Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="87ff2-113">This also allows users with minimal system access levels to safely run the application.</span></span>  
  
    ```vb  
    ' You should replace the bold text file
    ' in the sample below with a text file of your own choosing.  
    TreeView1.Nodes.Add(New myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\ TextFile.txt ") )  
    ```  
  
    ```csharp  
    // You should replace the bold text file
    // in the sample below with a text file of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    treeView1.Nodes.Add(new myTreeNode(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\TextFile.txt") );  
    ```  
  
    ```cpp  
    // You should replace the bold text file
    // in the sample below with a text file of your own choosing.  
    treeView1->Nodes->Add(new myTreeNode(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\TextFile.txt")));  
    ```  
  
2. <span data-ttu-id="87ff2-114">Si se pasa el nodo de árbol y <xref:System.Windows.Forms.TreeNode> se escribe como una clase, tendrá que convertir a la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="87ff2-114">If you are passed the tree node and it is typed as a <xref:System.Windows.Forms.TreeNode> class, then you will need to cast to your derived class.</span></span> <span data-ttu-id="87ff2-115">La conversión de tipos es una conversión explícita de un tipo de objeto a otro.</span><span class="sxs-lookup"><span data-stu-id="87ff2-115">Casting is an explicit conversion from one type of object to another.</span></span> <span data-ttu-id="87ff2-116">Para obtener más información sobre la conversión, vea [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), [Conversión y conversiones](../../../csharp/programming-guide/types/casting-and-type-conversions.md) de tipos (Visual C-) o Operador de [conversión: ()](/cpp/cpp/cast-operator-parens) (Visual C++).</span><span class="sxs-lookup"><span data-stu-id="87ff2-116">For more information on casting, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), [Casting and type conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) (Visual C#), or [Cast Operator: ()](/cpp/cpp/cast-operator-parens) (Visual C++).</span></span>  
  
    ```vb  
    Public Sub TreeView1_AfterSelect(ByVal sender As Object, ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       Dim mynode As myTreeNode  
       mynode = CType(e.node, myTreeNode)  
       MessageBox.Show("Node selected is " & mynode.filepath)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,  
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       myTreeNode myNode = (myTreeNode)e.Node;  
       MessageBox.Show("Node selected is " + myNode.FilePath);  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          myTreeNode ^ myNode = safe_cast<myTreeNode^>(e->Node);  
          MessageBox::Show(String::Concat("Node selected is ",
             myNode->FilePath));  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="87ff2-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87ff2-117">See also</span></span>

- [<span data-ttu-id="87ff2-118">TreeView (control)</span><span class="sxs-lookup"><span data-stu-id="87ff2-118">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="87ff2-119">Control ListView</span><span class="sxs-lookup"><span data-stu-id="87ff2-119">ListView Control</span></span>](listview-control-windows-forms.md)
