---
title: Colecciones de esquemas de OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164689"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="10a2c-102">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="10a2c-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="10a2c-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los proveedores OLE DB de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="10a2c-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="10a2c-104">Proveedor OLE DB para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="10a2c-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="10a2c-105">El controlador OLE DB de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="10a2c-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="10a2c-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="10a2c-106">Tables</span></span>  
  
-   <span data-ttu-id="10a2c-107">Columnas</span><span class="sxs-lookup"><span data-stu-id="10a2c-107">Columns</span></span>  
  
-   <span data-ttu-id="10a2c-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="10a2c-108">Procedures</span></span>  
  
-   <span data-ttu-id="10a2c-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="10a2c-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="10a2c-110">Catálogo</span><span class="sxs-lookup"><span data-stu-id="10a2c-110">Catalog</span></span>  
  
-   <span data-ttu-id="10a2c-111">Índices</span><span class="sxs-lookup"><span data-stu-id="10a2c-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="10a2c-112">Tablas</span><span class="sxs-lookup"><span data-stu-id="10a2c-112">Tables</span></span>  
  
|<span data-ttu-id="10a2c-113">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-113">ColumnName</span></span>|<span data-ttu-id="10a2c-114">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-115">TABLE_CATALOG</span></span>|<span data-ttu-id="10a2c-116">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-116">String</span></span>|  
|<span data-ttu-id="10a2c-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="10a2c-118">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-118">String</span></span>|  
|<span data-ttu-id="10a2c-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-119">TABLE_NAME</span></span>|<span data-ttu-id="10a2c-120">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-120">String</span></span>|  
|<span data-ttu-id="10a2c-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-121">TABLE_TYPE</span></span>|<span data-ttu-id="10a2c-122">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-122">String</span></span>|  
|<span data-ttu-id="10a2c-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-123">TABLE_GUID</span></span>|<span data-ttu-id="10a2c-124">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-124">Guid</span></span>|  
|<span data-ttu-id="10a2c-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-125">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-126">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-126">String</span></span>|  
|<span data-ttu-id="10a2c-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="10a2c-127">TABLE_PROPID</span></span>|<span data-ttu-id="10a2c-128">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-128">Int64</span></span>|  
|<span data-ttu-id="10a2c-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="10a2c-129">DATE_CREATED</span></span>|<span data-ttu-id="10a2c-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-130">DateTime</span></span>|  
|<span data-ttu-id="10a2c-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="10a2c-131">DATE_MODIFIED</span></span>|<span data-ttu-id="10a2c-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="10a2c-133">Columnas</span><span class="sxs-lookup"><span data-stu-id="10a2c-133">Columns</span></span>  
  
|<span data-ttu-id="10a2c-134">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-134">ColumnName</span></span>|<span data-ttu-id="10a2c-135">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-136">TABLE_CATALOG</span></span>|<span data-ttu-id="10a2c-137">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-137">String</span></span>|  
|<span data-ttu-id="10a2c-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="10a2c-139">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-139">String</span></span>|  
|<span data-ttu-id="10a2c-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-140">TABLE_NAME</span></span>|<span data-ttu-id="10a2c-141">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-141">String</span></span>|  
|<span data-ttu-id="10a2c-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-142">COLUMN_NAME</span></span>|<span data-ttu-id="10a2c-143">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-143">String</span></span>|  
|<span data-ttu-id="10a2c-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-144">COLUMN_GUID</span></span>|<span data-ttu-id="10a2c-145">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-145">Guid</span></span>|  
|<span data-ttu-id="10a2c-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="10a2c-146">COLUMN_PROPID</span></span>|<span data-ttu-id="10a2c-147">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-147">Int64</span></span>|  
|<span data-ttu-id="10a2c-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="10a2c-149">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-149">Int64</span></span>|  
|<span data-ttu-id="10a2c-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="10a2c-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="10a2c-151">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-151">Boolean</span></span>|  
|<span data-ttu-id="10a2c-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="10a2c-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="10a2c-153">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-153">String</span></span>|  
|<span data-ttu-id="10a2c-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="10a2c-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="10a2c-155">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-155">Int64</span></span>|  
|<span data-ttu-id="10a2c-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10a2c-156">IS_NULLABLE</span></span>|<span data-ttu-id="10a2c-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-157">Boolean</span></span>|  
|<span data-ttu-id="10a2c-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-158">DATA_TYPE</span></span>|<span data-ttu-id="10a2c-159">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-159">Int32</span></span>|  
|<span data-ttu-id="10a2c-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-160">TYPE_GUID</span></span>|<span data-ttu-id="10a2c-161">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-161">Guid</span></span>|  
|<span data-ttu-id="10a2c-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10a2c-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="10a2c-163">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-163">Int64</span></span>|  
|<span data-ttu-id="10a2c-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10a2c-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="10a2c-165">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-165">Int64</span></span>|  
|<span data-ttu-id="10a2c-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="10a2c-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="10a2c-167">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-167">Int32</span></span>|  
|<span data-ttu-id="10a2c-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="10a2c-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="10a2c-169">Int16</span><span class="sxs-lookup"><span data-stu-id="10a2c-169">Int16</span></span>|  
|<span data-ttu-id="10a2c-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="10a2c-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="10a2c-171">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-171">Int64</span></span>|  
|<span data-ttu-id="10a2c-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="10a2c-173">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-173">String</span></span>|  
|<span data-ttu-id="10a2c-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="10a2c-175">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-175">String</span></span>|  
|<span data-ttu-id="10a2c-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="10a2c-177">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-177">String</span></span>|  
|<span data-ttu-id="10a2c-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="10a2c-179">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-179">String</span></span>|  
|<span data-ttu-id="10a2c-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="10a2c-181">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-181">String</span></span>|  
|<span data-ttu-id="10a2c-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-182">COLLATION_NAME</span></span>|<span data-ttu-id="10a2c-183">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-183">String</span></span>|  
|<span data-ttu-id="10a2c-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="10a2c-185">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-185">String</span></span>|  
|<span data-ttu-id="10a2c-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="10a2c-187">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-187">String</span></span>|  
|<span data-ttu-id="10a2c-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-188">DOMAIN_NAME</span></span>|<span data-ttu-id="10a2c-189">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-189">String</span></span>|  
|<span data-ttu-id="10a2c-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-190">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-191">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-191">String</span></span>|  
|<span data-ttu-id="10a2c-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="10a2c-192">COLUMN_LCID</span></span>|<span data-ttu-id="10a2c-193">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-193">Int32</span></span>|  
|<span data-ttu-id="10a2c-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="10a2c-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="10a2c-195">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-195">Int32</span></span>|  
|<span data-ttu-id="10a2c-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="10a2c-196">COLUMN_SORTID</span></span>|<span data-ttu-id="10a2c-197">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-197">Int32</span></span>|  
|<span data-ttu-id="10a2c-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="10a2c-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="10a2c-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="10a2c-199">Byte[]</span></span>|  
|<span data-ttu-id="10a2c-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="10a2c-200">IS_COMPUTED</span></span>|<span data-ttu-id="10a2c-201">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="10a2c-202">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="10a2c-202">Procedures</span></span>  
  
|<span data-ttu-id="10a2c-203">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-203">ColumnName</span></span>|<span data-ttu-id="10a2c-204">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="10a2c-206">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-206">String</span></span>|  
|<span data-ttu-id="10a2c-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="10a2c-208">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-208">String</span></span>|  
|<span data-ttu-id="10a2c-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="10a2c-210">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-210">String</span></span>|  
|<span data-ttu-id="10a2c-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="10a2c-212">Int16</span><span class="sxs-lookup"><span data-stu-id="10a2c-212">Int16</span></span>|  
|<span data-ttu-id="10a2c-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="10a2c-214">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-214">String</span></span>|  
|<span data-ttu-id="10a2c-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-215">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-216">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-216">String</span></span>|  
|<span data-ttu-id="10a2c-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="10a2c-217">DATE_CREATED</span></span>|<span data-ttu-id="10a2c-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-218">DateTime</span></span>|  
|<span data-ttu-id="10a2c-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="10a2c-219">DATE_MODIFIED</span></span>|<span data-ttu-id="10a2c-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="10a2c-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="10a2c-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="10a2c-222">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-222">ColumnName</span></span>|<span data-ttu-id="10a2c-223">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="10a2c-225">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-225">String</span></span>|  
|<span data-ttu-id="10a2c-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="10a2c-227">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-227">String</span></span>|  
|<span data-ttu-id="10a2c-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="10a2c-229">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-229">String</span></span>|  
|<span data-ttu-id="10a2c-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-230">PARAMETER_NAME</span></span>|<span data-ttu-id="10a2c-231">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-231">String</span></span>|  
|<span data-ttu-id="10a2c-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="10a2c-233">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-233">Int32</span></span>|  
|<span data-ttu-id="10a2c-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="10a2c-235">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-235">Int32</span></span>|  
|<span data-ttu-id="10a2c-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="10a2c-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="10a2c-237">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-237">Boolean</span></span>|  
|<span data-ttu-id="10a2c-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="10a2c-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="10a2c-239">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-239">String</span></span>|  
|<span data-ttu-id="10a2c-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10a2c-240">IS_NULLABLE</span></span>|<span data-ttu-id="10a2c-241">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-241">Boolean</span></span>|  
|<span data-ttu-id="10a2c-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-242">DATA_TYPE</span></span>|<span data-ttu-id="10a2c-243">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-243">Int32</span></span>|  
|<span data-ttu-id="10a2c-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10a2c-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="10a2c-245">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-245">Int64</span></span>|  
|<span data-ttu-id="10a2c-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10a2c-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="10a2c-247">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-247">Int64</span></span>|  
|<span data-ttu-id="10a2c-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="10a2c-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="10a2c-249">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-249">Int32</span></span>|  
|<span data-ttu-id="10a2c-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="10a2c-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="10a2c-251">Int16</span><span class="sxs-lookup"><span data-stu-id="10a2c-251">Int16</span></span>|  
|<span data-ttu-id="10a2c-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-252">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-253">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-253">String</span></span>|  
|<span data-ttu-id="10a2c-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-254">TYPE_NAME</span></span>|<span data-ttu-id="10a2c-255">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-255">String</span></span>|  
|<span data-ttu-id="10a2c-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="10a2c-257">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="10a2c-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="10a2c-258">Catalog</span></span>  
  
|<span data-ttu-id="10a2c-259">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-259">ColumnName</span></span>|<span data-ttu-id="10a2c-260">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-261">CATALOG_NAME</span></span>|<span data-ttu-id="10a2c-262">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-262">String</span></span>|  
|<span data-ttu-id="10a2c-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-263">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-264">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="10a2c-265">Índices</span><span class="sxs-lookup"><span data-stu-id="10a2c-265">Indexes</span></span>  
  
|<span data-ttu-id="10a2c-266">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-266">ColumnName</span></span>|<span data-ttu-id="10a2c-267">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-268">TABLE_CATALOG</span></span>|<span data-ttu-id="10a2c-269">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-269">String</span></span>|  
|<span data-ttu-id="10a2c-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="10a2c-271">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-271">String</span></span>|  
|<span data-ttu-id="10a2c-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-272">TABLE_NAME</span></span>|<span data-ttu-id="10a2c-273">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-273">String</span></span>|  
|<span data-ttu-id="10a2c-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-274">INDEX_CATALOG</span></span>|<span data-ttu-id="10a2c-275">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-275">String</span></span>|  
|<span data-ttu-id="10a2c-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="10a2c-277">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-277">String</span></span>|  
|<span data-ttu-id="10a2c-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-278">INDEX_NAME</span></span>|<span data-ttu-id="10a2c-279">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-279">String</span></span>|  
|<span data-ttu-id="10a2c-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="10a2c-280">PRIMARY_KEY</span></span>|<span data-ttu-id="10a2c-281">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-281">Boolean</span></span>|  
|<span data-ttu-id="10a2c-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="10a2c-282">UNIQUE</span></span>|<span data-ttu-id="10a2c-283">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-283">Boolean</span></span>|  
|<span data-ttu-id="10a2c-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="10a2c-284">CLUSTERED</span></span>|<span data-ttu-id="10a2c-285">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-285">Boolean</span></span>|  
|<span data-ttu-id="10a2c-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-286">TYPE</span></span>|<span data-ttu-id="10a2c-287">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-287">Int32</span></span>|  
|<span data-ttu-id="10a2c-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="10a2c-288">FILL_FACTOR</span></span>|<span data-ttu-id="10a2c-289">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-289">Int32</span></span>|  
|<span data-ttu-id="10a2c-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="10a2c-290">INITIAL_SIZE</span></span>|<span data-ttu-id="10a2c-291">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-291">Int32</span></span>|  
|<span data-ttu-id="10a2c-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="10a2c-292">NULLS</span></span>|<span data-ttu-id="10a2c-293">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-293">Int32</span></span>|  
|<span data-ttu-id="10a2c-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="10a2c-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="10a2c-295">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-295">Boolean</span></span>|  
|<span data-ttu-id="10a2c-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="10a2c-296">AUTO_UPDATE</span></span>|<span data-ttu-id="10a2c-297">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-297">Boolean</span></span>|  
|<span data-ttu-id="10a2c-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="10a2c-298">NULL_COLLATION</span></span>|<span data-ttu-id="10a2c-299">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-299">Int32</span></span>|  
|<span data-ttu-id="10a2c-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="10a2c-301">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-301">Int64</span></span>|  
|<span data-ttu-id="10a2c-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-302">COLUMN_NAME</span></span>|<span data-ttu-id="10a2c-303">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-303">String</span></span>|  
|<span data-ttu-id="10a2c-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-304">COLUMN_GUID</span></span>|<span data-ttu-id="10a2c-305">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-305">Guid</span></span>|  
|<span data-ttu-id="10a2c-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="10a2c-306">COLUMN_PROPID</span></span>|<span data-ttu-id="10a2c-307">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-307">Int64</span></span>|  
|<span data-ttu-id="10a2c-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="10a2c-308">COLLATION</span></span>|<span data-ttu-id="10a2c-309">Int16</span><span class="sxs-lookup"><span data-stu-id="10a2c-309">Int16</span></span>|  
|<span data-ttu-id="10a2c-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="10a2c-310">CARDINALITY</span></span>|<span data-ttu-id="10a2c-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="10a2c-311">Decimal</span></span>|  
|<span data-ttu-id="10a2c-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="10a2c-312">PAGES</span></span>|<span data-ttu-id="10a2c-313">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-313">Int32</span></span>|  
|<span data-ttu-id="10a2c-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-314">FILTER_CONDITION</span></span>|<span data-ttu-id="10a2c-315">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-315">String</span></span>|  
|<span data-ttu-id="10a2c-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="10a2c-316">INTEGRATED</span></span>|<span data-ttu-id="10a2c-317">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="10a2c-318">Proveedor OLE DB de Microsoft para Oracle</span><span class="sxs-lookup"><span data-stu-id="10a2c-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="10a2c-319">El controlador OLE DB de Microsoft para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="10a2c-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="10a2c-320">Tablas</span><span class="sxs-lookup"><span data-stu-id="10a2c-320">Tables</span></span>  
  
-   <span data-ttu-id="10a2c-321">Columnas</span><span class="sxs-lookup"><span data-stu-id="10a2c-321">Columns</span></span>  
  
-   <span data-ttu-id="10a2c-322">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="10a2c-322">Procedures</span></span>  
  
-   <span data-ttu-id="10a2c-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="10a2c-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="10a2c-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="10a2c-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="10a2c-325">Vistas</span><span class="sxs-lookup"><span data-stu-id="10a2c-325">Views</span></span>  
  
-   <span data-ttu-id="10a2c-326">Índices</span><span class="sxs-lookup"><span data-stu-id="10a2c-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="10a2c-327">Tablas</span><span class="sxs-lookup"><span data-stu-id="10a2c-327">Tables</span></span>  
  
|<span data-ttu-id="10a2c-328">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-328">ColumnName</span></span>|<span data-ttu-id="10a2c-329">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-330">TABLE_CATALOG</span></span>|<span data-ttu-id="10a2c-331">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-331">String</span></span>|  
|<span data-ttu-id="10a2c-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="10a2c-333">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-333">String</span></span>|  
|<span data-ttu-id="10a2c-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-334">TABLE_NAME</span></span>|<span data-ttu-id="10a2c-335">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-335">String</span></span>|  
|<span data-ttu-id="10a2c-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-336">TABLE_TYPE</span></span>|<span data-ttu-id="10a2c-337">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-337">String</span></span>|  
|<span data-ttu-id="10a2c-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-338">TABLE_GUID</span></span>|<span data-ttu-id="10a2c-339">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-339">Guid</span></span>|  
|<span data-ttu-id="10a2c-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-340">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-341">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-341">String</span></span>|  
|<span data-ttu-id="10a2c-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="10a2c-342">TABLE_PROPID</span></span>|<span data-ttu-id="10a2c-343">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-343">Int64</span></span>|  
|<span data-ttu-id="10a2c-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="10a2c-344">DATE_CREATED</span></span>|<span data-ttu-id="10a2c-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-345">DateTime</span></span>|  
|<span data-ttu-id="10a2c-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="10a2c-346">DATE_MODIFIED</span></span>|<span data-ttu-id="10a2c-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="10a2c-348">Columnas</span><span class="sxs-lookup"><span data-stu-id="10a2c-348">Columns</span></span>  
  
|<span data-ttu-id="10a2c-349">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-349">ColumnName</span></span>|<span data-ttu-id="10a2c-350">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-351">TABLE_CATALOG</span></span>|<span data-ttu-id="10a2c-352">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-352">String</span></span>|  
|<span data-ttu-id="10a2c-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="10a2c-354">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-354">String</span></span>|  
|<span data-ttu-id="10a2c-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-355">TABLE_NAME</span></span>|<span data-ttu-id="10a2c-356">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-356">String</span></span>|  
|<span data-ttu-id="10a2c-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-357">COLUMN_NAME</span></span>|<span data-ttu-id="10a2c-358">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-358">String</span></span>|  
|<span data-ttu-id="10a2c-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-359">COLUMN_GUID</span></span>|<span data-ttu-id="10a2c-360">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-360">Guid</span></span>|  
|<span data-ttu-id="10a2c-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="10a2c-361">COLUMN_PROPID</span></span>|<span data-ttu-id="10a2c-362">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-362">Int64</span></span>|  
|<span data-ttu-id="10a2c-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="10a2c-364">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-364">Int64</span></span>|  
|<span data-ttu-id="10a2c-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="10a2c-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="10a2c-366">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-366">Boolean</span></span>|  
|<span data-ttu-id="10a2c-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="10a2c-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="10a2c-368">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-368">String</span></span>|  
|<span data-ttu-id="10a2c-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="10a2c-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="10a2c-370">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-370">Int64</span></span>|  
|<span data-ttu-id="10a2c-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10a2c-371">IS_NULLABLE</span></span>|<span data-ttu-id="10a2c-372">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-372">Boolean</span></span>|  
|<span data-ttu-id="10a2c-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-373">DATA_TYPE</span></span>|<span data-ttu-id="10a2c-374">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-374">Int32</span></span>|  
|<span data-ttu-id="10a2c-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-375">TYPE_GUID</span></span>|<span data-ttu-id="10a2c-376">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-376">Guid</span></span>|  
|<span data-ttu-id="10a2c-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10a2c-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="10a2c-378">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-378">Int64</span></span>|  
|<span data-ttu-id="10a2c-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10a2c-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="10a2c-380">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-380">Int64</span></span>|  
|<span data-ttu-id="10a2c-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="10a2c-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="10a2c-382">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-382">Int32</span></span>|  
|<span data-ttu-id="10a2c-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="10a2c-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="10a2c-384">Int16</span><span class="sxs-lookup"><span data-stu-id="10a2c-384">Int16</span></span>|  
|<span data-ttu-id="10a2c-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="10a2c-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="10a2c-386">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-386">Int64</span></span>|  
|<span data-ttu-id="10a2c-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="10a2c-388">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-388">String</span></span>|  
|<span data-ttu-id="10a2c-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="10a2c-390">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-390">String</span></span>|  
|<span data-ttu-id="10a2c-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="10a2c-392">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-392">String</span></span>|  
|<span data-ttu-id="10a2c-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="10a2c-394">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-394">String</span></span>|  
|<span data-ttu-id="10a2c-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="10a2c-396">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-396">String</span></span>|  
|<span data-ttu-id="10a2c-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-397">COLLATION_NAME</span></span>|<span data-ttu-id="10a2c-398">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-398">String</span></span>|  
|<span data-ttu-id="10a2c-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="10a2c-400">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-400">String</span></span>|  
|<span data-ttu-id="10a2c-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="10a2c-402">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-402">String</span></span>|  
|<span data-ttu-id="10a2c-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-403">DOMAIN_NAME</span></span>|<span data-ttu-id="10a2c-404">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-404">String</span></span>|  
|<span data-ttu-id="10a2c-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-405">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-406">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="10a2c-407">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="10a2c-407">Procedures</span></span>  
  
|<span data-ttu-id="10a2c-408">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-408">ColumnName</span></span>|<span data-ttu-id="10a2c-409">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="10a2c-411">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-411">String</span></span>|  
|<span data-ttu-id="10a2c-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="10a2c-413">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-413">String</span></span>|  
|<span data-ttu-id="10a2c-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="10a2c-415">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-415">String</span></span>|  
|<span data-ttu-id="10a2c-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="10a2c-417">Int16</span><span class="sxs-lookup"><span data-stu-id="10a2c-417">Int16</span></span>|  
|<span data-ttu-id="10a2c-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="10a2c-419">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-419">String</span></span>|  
|<span data-ttu-id="10a2c-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-420">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-421">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-421">String</span></span>|  
|<span data-ttu-id="10a2c-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="10a2c-422">DATE_CREATED</span></span>|<span data-ttu-id="10a2c-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-423">DateTime</span></span>|  
|<span data-ttu-id="10a2c-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="10a2c-424">DATE_MODIFIED</span></span>|<span data-ttu-id="10a2c-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="10a2c-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="10a2c-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="10a2c-427">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-427">ColumnName</span></span>|<span data-ttu-id="10a2c-428">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="10a2c-430">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-430">String</span></span>|  
|<span data-ttu-id="10a2c-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="10a2c-432">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-432">String</span></span>|  
|<span data-ttu-id="10a2c-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="10a2c-434">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-434">String</span></span>|  
|<span data-ttu-id="10a2c-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-435">COLUMN_NAME</span></span>|<span data-ttu-id="10a2c-436">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-436">String</span></span>|  
|<span data-ttu-id="10a2c-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-437">COLUMN_GUID</span></span>|<span data-ttu-id="10a2c-438">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-438">Guid</span></span>|  
|<span data-ttu-id="10a2c-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="10a2c-439">COLUMN_PROPID</span></span>|<span data-ttu-id="10a2c-440">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-440">Int64</span></span>|  
|<span data-ttu-id="10a2c-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="10a2c-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="10a2c-442">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-442">Int64</span></span>|  
|<span data-ttu-id="10a2c-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="10a2c-444">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-444">Int64</span></span>|  
|<span data-ttu-id="10a2c-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10a2c-445">IS_NULLABLE</span></span>|<span data-ttu-id="10a2c-446">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-446">Boolean</span></span>|  
|<span data-ttu-id="10a2c-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-447">DATA_TYPE</span></span>|<span data-ttu-id="10a2c-448">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-448">Int32</span></span>|  
|<span data-ttu-id="10a2c-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-449">TYPE_GUID</span></span>|<span data-ttu-id="10a2c-450">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-450">Guid</span></span>|  
|<span data-ttu-id="10a2c-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10a2c-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="10a2c-452">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-452">Int64</span></span>|  
|<span data-ttu-id="10a2c-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10a2c-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="10a2c-454">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-454">Int64</span></span>|  
|<span data-ttu-id="10a2c-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="10a2c-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="10a2c-456">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-456">Int32</span></span>|  
|<span data-ttu-id="10a2c-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="10a2c-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="10a2c-458">Int16</span><span class="sxs-lookup"><span data-stu-id="10a2c-458">Int16</span></span>|  
|<span data-ttu-id="10a2c-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-459">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-460">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-460">String</span></span>|  
|<span data-ttu-id="10a2c-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="10a2c-461">OVERLOAD</span></span>|<span data-ttu-id="10a2c-462">Int16</span><span class="sxs-lookup"><span data-stu-id="10a2c-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="10a2c-463">Vistas</span><span class="sxs-lookup"><span data-stu-id="10a2c-463">Views</span></span>  
  
|<span data-ttu-id="10a2c-464">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-464">ColumnName</span></span>|<span data-ttu-id="10a2c-465">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-466">TABLE_CATALOG</span></span>|<span data-ttu-id="10a2c-467">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-467">String</span></span>|  
|<span data-ttu-id="10a2c-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="10a2c-469">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-469">String</span></span>|  
|<span data-ttu-id="10a2c-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-470">TABLE_NAME</span></span>|<span data-ttu-id="10a2c-471">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-471">String</span></span>|  
|<span data-ttu-id="10a2c-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="10a2c-473">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-473">String</span></span>|  
|<span data-ttu-id="10a2c-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-474">CHECK_OPTION</span></span>|<span data-ttu-id="10a2c-475">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-475">Boolean</span></span>|  
|<span data-ttu-id="10a2c-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="10a2c-476">IS_UPDATABLE</span></span>|<span data-ttu-id="10a2c-477">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-477">Boolean</span></span>|  
|<span data-ttu-id="10a2c-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-478">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-479">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-479">String</span></span>|  
|<span data-ttu-id="10a2c-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="10a2c-480">DATE_CREATED</span></span>|<span data-ttu-id="10a2c-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-481">DateTime</span></span>|  
|<span data-ttu-id="10a2c-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="10a2c-482">DATE_MODIFIED</span></span>|<span data-ttu-id="10a2c-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="10a2c-484">Índices</span><span class="sxs-lookup"><span data-stu-id="10a2c-484">Indexes</span></span>  
  
|<span data-ttu-id="10a2c-485">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-485">ColumnName</span></span>|<span data-ttu-id="10a2c-486">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-487">TABLE_CATALOG</span></span>|<span data-ttu-id="10a2c-488">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-488">String</span></span>|  
|<span data-ttu-id="10a2c-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="10a2c-490">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-490">String</span></span>|  
|<span data-ttu-id="10a2c-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-491">TABLE_NAME</span></span>|<span data-ttu-id="10a2c-492">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-492">String</span></span>|  
|<span data-ttu-id="10a2c-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-493">INDEX_CATALOG</span></span>|<span data-ttu-id="10a2c-494">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-494">String</span></span>|  
|<span data-ttu-id="10a2c-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="10a2c-496">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-496">String</span></span>|  
|<span data-ttu-id="10a2c-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-497">INDEX_NAME</span></span>|<span data-ttu-id="10a2c-498">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-498">String</span></span>|  
|<span data-ttu-id="10a2c-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="10a2c-499">PRIMARY_KEY</span></span>|<span data-ttu-id="10a2c-500">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-500">Boolean</span></span>|  
|<span data-ttu-id="10a2c-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="10a2c-501">UNIQUE</span></span>|<span data-ttu-id="10a2c-502">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-502">Boolean</span></span>|  
|<span data-ttu-id="10a2c-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="10a2c-503">CLUSTERED</span></span>|<span data-ttu-id="10a2c-504">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-504">Boolean</span></span>|  
|<span data-ttu-id="10a2c-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-505">TYPE</span></span>|<span data-ttu-id="10a2c-506">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-506">Int32</span></span>|  
|<span data-ttu-id="10a2c-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="10a2c-507">FILL_FACTOR</span></span>|<span data-ttu-id="10a2c-508">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-508">Int32</span></span>|  
|<span data-ttu-id="10a2c-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="10a2c-509">INITIAL_SIZE</span></span>|<span data-ttu-id="10a2c-510">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-510">Int32</span></span>|  
|<span data-ttu-id="10a2c-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="10a2c-511">NULLS</span></span>|<span data-ttu-id="10a2c-512">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-512">Int32</span></span>|  
|<span data-ttu-id="10a2c-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="10a2c-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="10a2c-514">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-514">Boolean</span></span>|  
|<span data-ttu-id="10a2c-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="10a2c-515">AUTO_UPDATE</span></span>|<span data-ttu-id="10a2c-516">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-516">Boolean</span></span>|  
|<span data-ttu-id="10a2c-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="10a2c-517">NULL_COLLATION</span></span>|<span data-ttu-id="10a2c-518">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-518">Int32</span></span>|  
|<span data-ttu-id="10a2c-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="10a2c-520">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-520">Int64</span></span>|  
|<span data-ttu-id="10a2c-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-521">COLUMN_NAME</span></span>|<span data-ttu-id="10a2c-522">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-522">String</span></span>|  
|<span data-ttu-id="10a2c-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-523">COLUMN_GUID</span></span>|<span data-ttu-id="10a2c-524">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-524">Guid</span></span>|  
|<span data-ttu-id="10a2c-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="10a2c-525">COLUMN_PROPID</span></span>|<span data-ttu-id="10a2c-526">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-526">Int64</span></span>|  
|<span data-ttu-id="10a2c-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="10a2c-527">COLLATION</span></span>|<span data-ttu-id="10a2c-528">Int16</span><span class="sxs-lookup"><span data-stu-id="10a2c-528">Int16</span></span>|  
|<span data-ttu-id="10a2c-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="10a2c-529">CARDINALITY</span></span>|<span data-ttu-id="10a2c-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="10a2c-530">Decimal</span></span>|  
|<span data-ttu-id="10a2c-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="10a2c-531">PAGES</span></span>|<span data-ttu-id="10a2c-532">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-532">Int32</span></span>|  
|<span data-ttu-id="10a2c-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-533">FILTER_CONDITION</span></span>|<span data-ttu-id="10a2c-534">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-534">String</span></span>|  
|<span data-ttu-id="10a2c-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="10a2c-535">INTEGRATED</span></span>|<span data-ttu-id="10a2c-536">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="10a2c-537">Proveedor OLE DB de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="10a2c-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="10a2c-538">El controlador OLE DB de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="10a2c-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="10a2c-539">Tablas</span><span class="sxs-lookup"><span data-stu-id="10a2c-539">Tables</span></span>  
  
-   <span data-ttu-id="10a2c-540">Columnas</span><span class="sxs-lookup"><span data-stu-id="10a2c-540">Columns</span></span>  
  
-   <span data-ttu-id="10a2c-541">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="10a2c-541">Procedures</span></span>  
  
-   <span data-ttu-id="10a2c-542">Vistas</span><span class="sxs-lookup"><span data-stu-id="10a2c-542">Views</span></span>  
  
-   <span data-ttu-id="10a2c-543">Índices</span><span class="sxs-lookup"><span data-stu-id="10a2c-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="10a2c-544">Tablas</span><span class="sxs-lookup"><span data-stu-id="10a2c-544">Tables</span></span>  
  
|<span data-ttu-id="10a2c-545">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-545">ColumnName</span></span>|<span data-ttu-id="10a2c-546">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-547">TABLE_CATALOG</span></span>|<span data-ttu-id="10a2c-548">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-548">String</span></span>|  
|<span data-ttu-id="10a2c-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="10a2c-550">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-550">String</span></span>|  
|<span data-ttu-id="10a2c-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-551">TABLE_NAME</span></span>|<span data-ttu-id="10a2c-552">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-552">String</span></span>|  
|<span data-ttu-id="10a2c-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-553">TABLE_TYPE</span></span>|<span data-ttu-id="10a2c-554">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-554">String</span></span>|  
|<span data-ttu-id="10a2c-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-555">TABLE_GUID</span></span>|<span data-ttu-id="10a2c-556">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-556">Guid</span></span>|  
|<span data-ttu-id="10a2c-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-557">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-558">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-558">String</span></span>|  
|<span data-ttu-id="10a2c-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="10a2c-559">TABLE_PROPID</span></span>|<span data-ttu-id="10a2c-560">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-560">Int64</span></span>|  
|<span data-ttu-id="10a2c-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="10a2c-561">DATE_CREATED</span></span>|<span data-ttu-id="10a2c-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-562">DateTime</span></span>|  
|<span data-ttu-id="10a2c-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="10a2c-563">DATE_MODIFIED</span></span>|<span data-ttu-id="10a2c-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="10a2c-565">Columnas</span><span class="sxs-lookup"><span data-stu-id="10a2c-565">Columns</span></span>  
  
|<span data-ttu-id="10a2c-566">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-566">ColumnName</span></span>|<span data-ttu-id="10a2c-567">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-568">TABLE_CATALOG</span></span>|<span data-ttu-id="10a2c-569">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-569">String</span></span>|  
|<span data-ttu-id="10a2c-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="10a2c-571">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-571">String</span></span>|  
|<span data-ttu-id="10a2c-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-572">TABLE_NAME</span></span>|<span data-ttu-id="10a2c-573">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-573">String</span></span>|  
|<span data-ttu-id="10a2c-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-574">COLUMN_NAME</span></span>|<span data-ttu-id="10a2c-575">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-575">String</span></span>|  
|<span data-ttu-id="10a2c-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-576">COLUMN_GUID</span></span>|<span data-ttu-id="10a2c-577">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-577">Guid</span></span>|  
|<span data-ttu-id="10a2c-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="10a2c-578">COLUMN_PROPID</span></span>|<span data-ttu-id="10a2c-579">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-579">Int64</span></span>|  
|<span data-ttu-id="10a2c-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="10a2c-581">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-581">Int64</span></span>|  
|<span data-ttu-id="10a2c-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="10a2c-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="10a2c-583">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-583">Boolean</span></span>|  
|<span data-ttu-id="10a2c-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="10a2c-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="10a2c-585">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-585">String</span></span>|  
|<span data-ttu-id="10a2c-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="10a2c-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="10a2c-587">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-587">Int64</span></span>|  
|<span data-ttu-id="10a2c-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="10a2c-588">IS_NULLABLE</span></span>|<span data-ttu-id="10a2c-589">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-589">Boolean</span></span>|  
|<span data-ttu-id="10a2c-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-590">DATA_TYPE</span></span>|<span data-ttu-id="10a2c-591">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-591">Int32</span></span>|  
|<span data-ttu-id="10a2c-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-592">TYPE_GUID</span></span>|<span data-ttu-id="10a2c-593">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-593">Guid</span></span>|  
|<span data-ttu-id="10a2c-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10a2c-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="10a2c-595">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-595">Int64</span></span>|  
|<span data-ttu-id="10a2c-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="10a2c-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="10a2c-597">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-597">Int64</span></span>|  
|<span data-ttu-id="10a2c-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="10a2c-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="10a2c-599">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-599">Int32</span></span>|  
|<span data-ttu-id="10a2c-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="10a2c-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="10a2c-601">Int16</span><span class="sxs-lookup"><span data-stu-id="10a2c-601">Int16</span></span>|  
|<span data-ttu-id="10a2c-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="10a2c-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="10a2c-603">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-603">Int64</span></span>|  
|<span data-ttu-id="10a2c-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="10a2c-605">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-605">String</span></span>|  
|<span data-ttu-id="10a2c-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="10a2c-607">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-607">String</span></span>|  
|<span data-ttu-id="10a2c-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="10a2c-609">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-609">String</span></span>|  
|<span data-ttu-id="10a2c-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="10a2c-611">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-611">String</span></span>|  
|<span data-ttu-id="10a2c-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="10a2c-613">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-613">String</span></span>|  
|<span data-ttu-id="10a2c-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-614">COLLATION_NAME</span></span>|<span data-ttu-id="10a2c-615">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-615">String</span></span>|  
|<span data-ttu-id="10a2c-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="10a2c-617">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-617">String</span></span>|  
|<span data-ttu-id="10a2c-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="10a2c-619">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-619">String</span></span>|  
|<span data-ttu-id="10a2c-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-620">DOMAIN_NAME</span></span>|<span data-ttu-id="10a2c-621">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-621">String</span></span>|  
|<span data-ttu-id="10a2c-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-622">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-623">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="10a2c-624">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="10a2c-624">Procedures</span></span>  
  
|<span data-ttu-id="10a2c-625">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-625">ColumnName</span></span>|<span data-ttu-id="10a2c-626">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="10a2c-628">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-628">String</span></span>|  
|<span data-ttu-id="10a2c-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="10a2c-630">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-630">String</span></span>|  
|<span data-ttu-id="10a2c-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="10a2c-632">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-632">String</span></span>|  
|<span data-ttu-id="10a2c-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="10a2c-634">Int16</span><span class="sxs-lookup"><span data-stu-id="10a2c-634">Int16</span></span>|  
|<span data-ttu-id="10a2c-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="10a2c-636">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-636">String</span></span>|  
|<span data-ttu-id="10a2c-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-637">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-638">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-638">String</span></span>|  
|<span data-ttu-id="10a2c-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="10a2c-639">DATE_CREATED</span></span>|<span data-ttu-id="10a2c-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-640">DateTime</span></span>|  
|<span data-ttu-id="10a2c-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="10a2c-641">DATE_MODIFIED</span></span>|<span data-ttu-id="10a2c-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="10a2c-643">Vistas</span><span class="sxs-lookup"><span data-stu-id="10a2c-643">Views</span></span>  
  
|<span data-ttu-id="10a2c-644">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-644">ColumnName</span></span>|<span data-ttu-id="10a2c-645">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-646">TABLE_CATALOG</span></span>|<span data-ttu-id="10a2c-647">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-647">String</span></span>|  
|<span data-ttu-id="10a2c-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="10a2c-649">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-649">String</span></span>|  
|<span data-ttu-id="10a2c-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-650">TABLE_NAME</span></span>|<span data-ttu-id="10a2c-651">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-651">String</span></span>|  
|<span data-ttu-id="10a2c-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="10a2c-653">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-653">String</span></span>|  
|<span data-ttu-id="10a2c-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-654">CHECK_OPTION</span></span>|<span data-ttu-id="10a2c-655">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-655">Boolean</span></span>|  
|<span data-ttu-id="10a2c-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="10a2c-656">IS_UPDATABLE</span></span>|<span data-ttu-id="10a2c-657">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-657">Boolean</span></span>|  
|<span data-ttu-id="10a2c-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10a2c-658">DESCRIPTION</span></span>|<span data-ttu-id="10a2c-659">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-659">String</span></span>|  
|<span data-ttu-id="10a2c-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="10a2c-660">DATE_CREATED</span></span>|<span data-ttu-id="10a2c-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-661">DateTime</span></span>|  
|<span data-ttu-id="10a2c-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="10a2c-662">DATE_MODIFIED</span></span>|<span data-ttu-id="10a2c-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="10a2c-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="10a2c-664">Índices</span><span class="sxs-lookup"><span data-stu-id="10a2c-664">Indexes</span></span>  
  
|<span data-ttu-id="10a2c-665">ColumName</span><span class="sxs-lookup"><span data-stu-id="10a2c-665">ColumnName</span></span>|<span data-ttu-id="10a2c-666">DataType</span><span class="sxs-lookup"><span data-stu-id="10a2c-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="10a2c-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-667">TABLE_CATALOG</span></span>|<span data-ttu-id="10a2c-668">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-668">String</span></span>|  
|<span data-ttu-id="10a2c-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="10a2c-670">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-670">String</span></span>|  
|<span data-ttu-id="10a2c-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-671">TABLE_NAME</span></span>|<span data-ttu-id="10a2c-672">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-672">String</span></span>|  
|<span data-ttu-id="10a2c-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="10a2c-673">INDEX_CATALOG</span></span>|<span data-ttu-id="10a2c-674">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-674">String</span></span>|  
|<span data-ttu-id="10a2c-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="10a2c-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="10a2c-676">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-676">String</span></span>|  
|<span data-ttu-id="10a2c-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-677">INDEX_NAME</span></span>|<span data-ttu-id="10a2c-678">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-678">String</span></span>|  
|<span data-ttu-id="10a2c-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="10a2c-679">PRIMARY_KEY</span></span>|<span data-ttu-id="10a2c-680">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-680">Boolean</span></span>|  
|<span data-ttu-id="10a2c-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="10a2c-681">UNIQUE</span></span>|<span data-ttu-id="10a2c-682">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-682">Boolean</span></span>|  
|<span data-ttu-id="10a2c-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="10a2c-683">CLUSTERED</span></span>|<span data-ttu-id="10a2c-684">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-684">Boolean</span></span>|  
|<span data-ttu-id="10a2c-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="10a2c-685">TYPE</span></span>|<span data-ttu-id="10a2c-686">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-686">Int32</span></span>|  
|<span data-ttu-id="10a2c-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="10a2c-687">FILL_FACTOR</span></span>|<span data-ttu-id="10a2c-688">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-688">Int32</span></span>|  
|<span data-ttu-id="10a2c-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="10a2c-689">INITIAL_SIZE</span></span>|<span data-ttu-id="10a2c-690">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-690">Int32</span></span>|  
|<span data-ttu-id="10a2c-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="10a2c-691">NULLS</span></span>|<span data-ttu-id="10a2c-692">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-692">Int32</span></span>|  
|<span data-ttu-id="10a2c-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="10a2c-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="10a2c-694">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-694">Boolean</span></span>|  
|<span data-ttu-id="10a2c-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="10a2c-695">AUTO_UPDATE</span></span>|<span data-ttu-id="10a2c-696">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-696">Boolean</span></span>|  
|<span data-ttu-id="10a2c-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="10a2c-697">NULL_COLLATION</span></span>|<span data-ttu-id="10a2c-698">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-698">Int32</span></span>|  
|<span data-ttu-id="10a2c-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="10a2c-700">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-700">Int64</span></span>|  
|<span data-ttu-id="10a2c-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="10a2c-701">COLUMN_NAME</span></span>|<span data-ttu-id="10a2c-702">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-702">String</span></span>|  
|<span data-ttu-id="10a2c-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-703">COLUMN_GUID</span></span>|<span data-ttu-id="10a2c-704">GUID</span><span class="sxs-lookup"><span data-stu-id="10a2c-704">Guid</span></span>|  
|<span data-ttu-id="10a2c-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="10a2c-705">COLUMN_PROPID</span></span>|<span data-ttu-id="10a2c-706">Int64</span><span class="sxs-lookup"><span data-stu-id="10a2c-706">Int64</span></span>|  
|<span data-ttu-id="10a2c-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="10a2c-707">COLLATION</span></span>|<span data-ttu-id="10a2c-708">Int16</span><span class="sxs-lookup"><span data-stu-id="10a2c-708">Int16</span></span>|  
|<span data-ttu-id="10a2c-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="10a2c-709">CARDINALITY</span></span>|<span data-ttu-id="10a2c-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="10a2c-710">Decimal</span></span>|  
|<span data-ttu-id="10a2c-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="10a2c-711">PAGES</span></span>|<span data-ttu-id="10a2c-712">Int32</span><span class="sxs-lookup"><span data-stu-id="10a2c-712">Int32</span></span>|  
|<span data-ttu-id="10a2c-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="10a2c-713">FILTER_CONDITION</span></span>|<span data-ttu-id="10a2c-714">String</span><span class="sxs-lookup"><span data-stu-id="10a2c-714">String</span></span>|  
|<span data-ttu-id="10a2c-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="10a2c-715">INTEGRATED</span></span>|<span data-ttu-id="10a2c-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="10a2c-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10a2c-717">Vea también</span><span class="sxs-lookup"><span data-stu-id="10a2c-717">See also</span></span>

- [<span data-ttu-id="10a2c-718">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="10a2c-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
