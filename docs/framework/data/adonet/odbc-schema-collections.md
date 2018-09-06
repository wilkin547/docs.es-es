---
title: Colecciones de esquemas de ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877536"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="74326-102">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="74326-102">ODBC Schema Collections</span></span>
<span data-ttu-id="74326-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="74326-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="74326-104">Controlador ODBC para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="74326-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="74326-105">El controlador ODBC de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="74326-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="74326-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="74326-106">Tables</span></span>  
  
-   <span data-ttu-id="74326-107">Índices</span><span class="sxs-lookup"><span data-stu-id="74326-107">Indexes</span></span>  
  
-   <span data-ttu-id="74326-108">Columnas</span><span class="sxs-lookup"><span data-stu-id="74326-108">Columns</span></span>  
  
-   <span data-ttu-id="74326-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="74326-109">Procedures</span></span>  
  
-   <span data-ttu-id="74326-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="74326-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="74326-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="74326-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="74326-112">Vistas</span><span class="sxs-lookup"><span data-stu-id="74326-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="74326-113">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="74326-113">Tables and Views</span></span>  
  
|<span data-ttu-id="74326-114">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-114">ColumnName</span></span>|<span data-ttu-id="74326-115">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="74326-116">TABLE_CAT</span></span>|<span data-ttu-id="74326-117">String</span><span class="sxs-lookup"><span data-stu-id="74326-117">String</span></span>|  
|<span data-ttu-id="74326-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74326-118">TABLE_SCHEM</span></span>|<span data-ttu-id="74326-119">String</span><span class="sxs-lookup"><span data-stu-id="74326-119">String</span></span>|  
|<span data-ttu-id="74326-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-120">TABLE_NAME</span></span>|<span data-ttu-id="74326-121">String</span><span class="sxs-lookup"><span data-stu-id="74326-121">String</span></span>|  
|<span data-ttu-id="74326-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-122">TABLE_TYPE</span></span>|<span data-ttu-id="74326-123">String</span><span class="sxs-lookup"><span data-stu-id="74326-123">String</span></span>|  
|<span data-ttu-id="74326-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-124">REMARKS</span></span>|<span data-ttu-id="74326-125">String</span><span class="sxs-lookup"><span data-stu-id="74326-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="74326-126">Índices</span><span class="sxs-lookup"><span data-stu-id="74326-126">Indexes</span></span>  
  
|<span data-ttu-id="74326-127">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-127">ColumnName</span></span>|<span data-ttu-id="74326-128">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="74326-129">TABLE_CAT</span></span>|<span data-ttu-id="74326-130">String</span><span class="sxs-lookup"><span data-stu-id="74326-130">String</span></span>|  
|<span data-ttu-id="74326-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74326-131">TABLE_SCHEM</span></span>|<span data-ttu-id="74326-132">String</span><span class="sxs-lookup"><span data-stu-id="74326-132">String</span></span>|  
|<span data-ttu-id="74326-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-133">TABLE_NAME</span></span>|<span data-ttu-id="74326-134">String</span><span class="sxs-lookup"><span data-stu-id="74326-134">String</span></span>|  
|<span data-ttu-id="74326-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="74326-135">NON_UNIQUE</span></span>|<span data-ttu-id="74326-136">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-136">Int16</span></span>|  
|<span data-ttu-id="74326-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74326-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="74326-138">String</span><span class="sxs-lookup"><span data-stu-id="74326-138">String</span></span>|  
|<span data-ttu-id="74326-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-139">INDEX_NAME</span></span>|<span data-ttu-id="74326-140">String</span><span class="sxs-lookup"><span data-stu-id="74326-140">String</span></span>|  
|<span data-ttu-id="74326-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-141">TYPE</span></span>|<span data-ttu-id="74326-142">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-142">Int16</span></span>|  
|<span data-ttu-id="74326-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74326-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="74326-144">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-144">Int16</span></span>|  
|<span data-ttu-id="74326-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-145">COLUMN_NAME</span></span>|<span data-ttu-id="74326-146">String</span><span class="sxs-lookup"><span data-stu-id="74326-146">String</span></span>|  
|<span data-ttu-id="74326-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="74326-147">ASC_OR_DESC</span></span>|<span data-ttu-id="74326-148">String</span><span class="sxs-lookup"><span data-stu-id="74326-148">String</span></span>|  
|<span data-ttu-id="74326-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="74326-149">CARDINATLITY</span></span>|<span data-ttu-id="74326-150">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-150">Int32</span></span>|  
|<span data-ttu-id="74326-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="74326-151">PAGES</span></span>|<span data-ttu-id="74326-152">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-152">Int32</span></span>|  
|<span data-ttu-id="74326-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="74326-153">FILTER_CONDITION</span></span>|<span data-ttu-id="74326-154">String</span><span class="sxs-lookup"><span data-stu-id="74326-154">String</span></span>|  
|<span data-ttu-id="74326-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="74326-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="74326-156">String</span><span class="sxs-lookup"><span data-stu-id="74326-156">String</span></span>|  
|<span data-ttu-id="74326-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="74326-158">Byte</span><span class="sxs-lookup"><span data-stu-id="74326-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="74326-159">Columnas</span><span class="sxs-lookup"><span data-stu-id="74326-159">Columns</span></span>  
  
|<span data-ttu-id="74326-160">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-160">ColumnName</span></span>|<span data-ttu-id="74326-161">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="74326-162">TABLE_CAT</span></span>|<span data-ttu-id="74326-163">String</span><span class="sxs-lookup"><span data-stu-id="74326-163">String</span></span>|  
|<span data-ttu-id="74326-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74326-164">TABLE_SCHEM</span></span>|<span data-ttu-id="74326-165">String</span><span class="sxs-lookup"><span data-stu-id="74326-165">String</span></span>|  
|<span data-ttu-id="74326-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-166">TABLE_NAME</span></span>|<span data-ttu-id="74326-167">String</span><span class="sxs-lookup"><span data-stu-id="74326-167">String</span></span>|  
|<span data-ttu-id="74326-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-168">COLUMN_NAME</span></span>|<span data-ttu-id="74326-169">String</span><span class="sxs-lookup"><span data-stu-id="74326-169">String</span></span>|  
|<span data-ttu-id="74326-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-170">DATA_TYPE</span></span>|<span data-ttu-id="74326-171">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-171">Int16</span></span>|  
|<span data-ttu-id="74326-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-172">TYPE_NAME</span></span>|<span data-ttu-id="74326-173">String</span><span class="sxs-lookup"><span data-stu-id="74326-173">String</span></span>|  
|<span data-ttu-id="74326-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="74326-174">COLUMN_SIZE</span></span>|<span data-ttu-id="74326-175">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-175">Int32</span></span>|  
|<span data-ttu-id="74326-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74326-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="74326-177">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-177">Int32</span></span>|  
|<span data-ttu-id="74326-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="74326-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="74326-179">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-179">Int16</span></span>|  
|<span data-ttu-id="74326-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="74326-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="74326-181">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-181">Int16</span></span>|  
|<span data-ttu-id="74326-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74326-182">NULLABLE</span></span>|<span data-ttu-id="74326-183">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-183">Int16</span></span>|  
|<span data-ttu-id="74326-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-184">REMARKS</span></span>|<span data-ttu-id="74326-185">String</span><span class="sxs-lookup"><span data-stu-id="74326-185">String</span></span>|  
|<span data-ttu-id="74326-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="74326-186">COLUMN_DEF</span></span>|<span data-ttu-id="74326-187">String</span><span class="sxs-lookup"><span data-stu-id="74326-187">String</span></span>|  
|<span data-ttu-id="74326-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="74326-189">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-189">Int16</span></span>|  
|<span data-ttu-id="74326-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="74326-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="74326-191">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-191">Int16</span></span>|  
|<span data-ttu-id="74326-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74326-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="74326-193">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-193">Int32</span></span>|  
|<span data-ttu-id="74326-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74326-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="74326-195">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-195">Int32</span></span>|  
|<span data-ttu-id="74326-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74326-196">IS_NULLABLE</span></span>|<span data-ttu-id="74326-197">String</span><span class="sxs-lookup"><span data-stu-id="74326-197">String</span></span>|  
|<span data-ttu-id="74326-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="74326-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="74326-199">String</span><span class="sxs-lookup"><span data-stu-id="74326-199">String</span></span>|  
|<span data-ttu-id="74326-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="74326-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="74326-201">String</span><span class="sxs-lookup"><span data-stu-id="74326-201">String</span></span>|  
|<span data-ttu-id="74326-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="74326-203">Byte</span><span class="sxs-lookup"><span data-stu-id="74326-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="74326-204">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="74326-204">Procedures</span></span>  
  
|<span data-ttu-id="74326-205">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-205">ColumnName</span></span>|<span data-ttu-id="74326-206">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="74326-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="74326-208">String</span><span class="sxs-lookup"><span data-stu-id="74326-208">String</span></span>|  
|<span data-ttu-id="74326-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74326-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="74326-210">String</span><span class="sxs-lookup"><span data-stu-id="74326-210">String</span></span>|  
|<span data-ttu-id="74326-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="74326-212">String</span><span class="sxs-lookup"><span data-stu-id="74326-212">String</span></span>|  
|<span data-ttu-id="74326-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="74326-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="74326-214">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-214">Int32</span></span>|  
|<span data-ttu-id="74326-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="74326-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="74326-216">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-216">Int32</span></span>|  
|<span data-ttu-id="74326-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="74326-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="74326-218">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-218">Int32</span></span>|  
|<span data-ttu-id="74326-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-219">REMARKS</span></span>|<span data-ttu-id="74326-220">String</span><span class="sxs-lookup"><span data-stu-id="74326-220">String</span></span>|  
|<span data-ttu-id="74326-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="74326-222">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="74326-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="74326-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="74326-224">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-224">ColumnName</span></span>|<span data-ttu-id="74326-225">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="74326-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="74326-227">String</span><span class="sxs-lookup"><span data-stu-id="74326-227">String</span></span>|  
|<span data-ttu-id="74326-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74326-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="74326-229">String</span><span class="sxs-lookup"><span data-stu-id="74326-229">String</span></span>|  
|<span data-ttu-id="74326-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="74326-231">String</span><span class="sxs-lookup"><span data-stu-id="74326-231">String</span></span>|  
|<span data-ttu-id="74326-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-232">COLUMN_NAME</span></span>|<span data-ttu-id="74326-233">String</span><span class="sxs-lookup"><span data-stu-id="74326-233">String</span></span>|  
|<span data-ttu-id="74326-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-234">COLUMN_TYPE</span></span>|<span data-ttu-id="74326-235">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-235">Int16</span></span>|  
|<span data-ttu-id="74326-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-236">DATA_TYPE</span></span>|<span data-ttu-id="74326-237">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-237">Int16</span></span>|  
|<span data-ttu-id="74326-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-238">TYPE_NAME</span></span>|<span data-ttu-id="74326-239">String</span><span class="sxs-lookup"><span data-stu-id="74326-239">String</span></span>|  
|<span data-ttu-id="74326-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="74326-240">COLUMN_SIZE</span></span>|<span data-ttu-id="74326-241">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-241">Int32</span></span>|  
|<span data-ttu-id="74326-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74326-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="74326-243">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-243">Int32</span></span>|  
|<span data-ttu-id="74326-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="74326-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="74326-245">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-245">Int16</span></span>|  
|<span data-ttu-id="74326-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="74326-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="74326-247">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-247">Int16</span></span>|  
|<span data-ttu-id="74326-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74326-248">NULLABLE</span></span>|<span data-ttu-id="74326-249">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-249">Int16</span></span>|  
|<span data-ttu-id="74326-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-250">REMARKS</span></span>|<span data-ttu-id="74326-251">String</span><span class="sxs-lookup"><span data-stu-id="74326-251">String</span></span>|  
|<span data-ttu-id="74326-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="74326-252">COLUMN_DEF</span></span>|<span data-ttu-id="74326-253">String</span><span class="sxs-lookup"><span data-stu-id="74326-253">String</span></span>|  
|<span data-ttu-id="74326-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="74326-255">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-255">Int16</span></span>|  
|<span data-ttu-id="74326-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="74326-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="74326-257">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-257">Int16</span></span>|  
|<span data-ttu-id="74326-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74326-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="74326-259">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-259">Int32</span></span>|  
|<span data-ttu-id="74326-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74326-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="74326-261">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-261">Int32</span></span>|  
|<span data-ttu-id="74326-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74326-262">IS_NULLABLE</span></span>|<span data-ttu-id="74326-263">String</span><span class="sxs-lookup"><span data-stu-id="74326-263">String</span></span>|  
|<span data-ttu-id="74326-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="74326-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="74326-265">String</span><span class="sxs-lookup"><span data-stu-id="74326-265">String</span></span>|  
|<span data-ttu-id="74326-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="74326-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="74326-267">String</span><span class="sxs-lookup"><span data-stu-id="74326-267">String</span></span>|  
|<span data-ttu-id="74326-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="74326-269">Byte</span><span class="sxs-lookup"><span data-stu-id="74326-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="74326-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="74326-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="74326-271">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-271">ColumnName</span></span>|<span data-ttu-id="74326-272">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="74326-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="74326-274">String</span><span class="sxs-lookup"><span data-stu-id="74326-274">String</span></span>|  
|<span data-ttu-id="74326-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74326-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="74326-276">String</span><span class="sxs-lookup"><span data-stu-id="74326-276">String</span></span>|  
|<span data-ttu-id="74326-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="74326-278">String</span><span class="sxs-lookup"><span data-stu-id="74326-278">String</span></span>|  
|<span data-ttu-id="74326-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-279">COLUMN_NAME</span></span>|<span data-ttu-id="74326-280">String</span><span class="sxs-lookup"><span data-stu-id="74326-280">String</span></span>|  
|<span data-ttu-id="74326-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-281">COLUMN_TYPE</span></span>|<span data-ttu-id="74326-282">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-282">Int16</span></span>|  
|<span data-ttu-id="74326-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-283">DATA_TYPE</span></span>|<span data-ttu-id="74326-284">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-284">Int16</span></span>|  
|<span data-ttu-id="74326-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-285">TYPE_NAME</span></span>|<span data-ttu-id="74326-286">String</span><span class="sxs-lookup"><span data-stu-id="74326-286">String</span></span>|  
|<span data-ttu-id="74326-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="74326-287">COLUMN_SIZE</span></span>|<span data-ttu-id="74326-288">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-288">Int32</span></span>|  
|<span data-ttu-id="74326-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74326-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="74326-290">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-290">Int32</span></span>|  
|<span data-ttu-id="74326-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="74326-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="74326-292">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-292">Int16</span></span>|  
|<span data-ttu-id="74326-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="74326-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="74326-294">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-294">Int16</span></span>|  
|<span data-ttu-id="74326-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74326-295">NULLABLE</span></span>|<span data-ttu-id="74326-296">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-296">Int16</span></span>|  
|<span data-ttu-id="74326-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-297">REMARKS</span></span>|<span data-ttu-id="74326-298">String</span><span class="sxs-lookup"><span data-stu-id="74326-298">String</span></span>|  
|<span data-ttu-id="74326-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="74326-299">COLUMN_DEF</span></span>|<span data-ttu-id="74326-300">String</span><span class="sxs-lookup"><span data-stu-id="74326-300">String</span></span>|  
|<span data-ttu-id="74326-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="74326-302">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-302">Int16</span></span>|  
|<span data-ttu-id="74326-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="74326-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="74326-304">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-304">Int16</span></span>|  
|<span data-ttu-id="74326-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74326-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="74326-306">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-306">Int32</span></span>|  
|<span data-ttu-id="74326-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74326-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="74326-308">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-308">Int32</span></span>|  
|<span data-ttu-id="74326-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74326-309">IS_NULLABLE</span></span>|<span data-ttu-id="74326-310">String</span><span class="sxs-lookup"><span data-stu-id="74326-310">String</span></span>|  
|<span data-ttu-id="74326-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="74326-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="74326-312">String</span><span class="sxs-lookup"><span data-stu-id="74326-312">String</span></span>|  
|<span data-ttu-id="74326-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="74326-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="74326-314">String</span><span class="sxs-lookup"><span data-stu-id="74326-314">String</span></span>|  
|<span data-ttu-id="74326-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="74326-316">Byte</span><span class="sxs-lookup"><span data-stu-id="74326-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="74326-317">Controlador ODBC para Oracle de Microsoft</span><span class="sxs-lookup"><span data-stu-id="74326-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="74326-318">El controlador ODBC de Oracle de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="74326-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="74326-319">Tablas</span><span class="sxs-lookup"><span data-stu-id="74326-319">Tables</span></span>  
  
-   <span data-ttu-id="74326-320">Columnas</span><span class="sxs-lookup"><span data-stu-id="74326-320">Columns</span></span>  
  
-   <span data-ttu-id="74326-321">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="74326-321">Procedures</span></span>  
  
-   <span data-ttu-id="74326-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="74326-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="74326-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="74326-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="74326-324">Vistas</span><span class="sxs-lookup"><span data-stu-id="74326-324">Views</span></span>  
  
-   <span data-ttu-id="74326-325">Índices</span><span class="sxs-lookup"><span data-stu-id="74326-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="74326-326">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="74326-326">Tables and Views</span></span>  
  
|<span data-ttu-id="74326-327">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-327">ColumnName</span></span>|<span data-ttu-id="74326-328">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74326-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="74326-330">String</span><span class="sxs-lookup"><span data-stu-id="74326-330">String</span></span>|  
|<span data-ttu-id="74326-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74326-331">TABLE_OWNER</span></span>|<span data-ttu-id="74326-332">String</span><span class="sxs-lookup"><span data-stu-id="74326-332">String</span></span>|  
|<span data-ttu-id="74326-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-333">TABLE_NAME</span></span>|<span data-ttu-id="74326-334">String</span><span class="sxs-lookup"><span data-stu-id="74326-334">String</span></span>|  
|<span data-ttu-id="74326-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-335">TABLE_TYPE</span></span>|<span data-ttu-id="74326-336">String</span><span class="sxs-lookup"><span data-stu-id="74326-336">String</span></span>|  
|<span data-ttu-id="74326-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-337">REMARKS</span></span>|<span data-ttu-id="74326-338">String</span><span class="sxs-lookup"><span data-stu-id="74326-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="74326-339">Columnas</span><span class="sxs-lookup"><span data-stu-id="74326-339">Columns</span></span>  
  
|<span data-ttu-id="74326-340">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-340">ColumnName</span></span>|<span data-ttu-id="74326-341">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74326-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="74326-343">String</span><span class="sxs-lookup"><span data-stu-id="74326-343">String</span></span>|  
|<span data-ttu-id="74326-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74326-344">TABLE_OWNER</span></span>|<span data-ttu-id="74326-345">String</span><span class="sxs-lookup"><span data-stu-id="74326-345">String</span></span>|  
|<span data-ttu-id="74326-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-346">TABLE_NAME</span></span>|<span data-ttu-id="74326-347">String</span><span class="sxs-lookup"><span data-stu-id="74326-347">String</span></span>|  
|<span data-ttu-id="74326-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-348">COLUMN_NAME</span></span>|<span data-ttu-id="74326-349">String</span><span class="sxs-lookup"><span data-stu-id="74326-349">String</span></span>|  
|<span data-ttu-id="74326-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-350">DATA_TYPE</span></span>|<span data-ttu-id="74326-351">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-351">Int16</span></span>|  
|<span data-ttu-id="74326-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-352">TYPE_NAME</span></span>|<span data-ttu-id="74326-353">String</span><span class="sxs-lookup"><span data-stu-id="74326-353">String</span></span>|  
|<span data-ttu-id="74326-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="74326-354">PRECISION</span></span>|<span data-ttu-id="74326-355">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-355">Int32</span></span>|  
|<span data-ttu-id="74326-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="74326-356">LENGTH</span></span>|<span data-ttu-id="74326-357">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-357">Int32</span></span>|  
|<span data-ttu-id="74326-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="74326-358">SCALE</span></span>|<span data-ttu-id="74326-359">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-359">Int16</span></span>|  
|<span data-ttu-id="74326-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="74326-360">RADIX</span></span>|<span data-ttu-id="74326-361">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-361">Int16</span></span>|  
|<span data-ttu-id="74326-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74326-362">NULLABLE</span></span>|<span data-ttu-id="74326-363">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-363">Int16</span></span>|  
|<span data-ttu-id="74326-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-364">REMARKS</span></span>|<span data-ttu-id="74326-365">String</span><span class="sxs-lookup"><span data-stu-id="74326-365">String</span></span>|  
|<span data-ttu-id="74326-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74326-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="74326-367">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="74326-368">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="74326-368">Procedures</span></span>  
  
|<span data-ttu-id="74326-369">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-369">ColumnName</span></span>|<span data-ttu-id="74326-370">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74326-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="74326-372">String</span><span class="sxs-lookup"><span data-stu-id="74326-372">String</span></span>|  
|<span data-ttu-id="74326-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74326-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="74326-374">String</span><span class="sxs-lookup"><span data-stu-id="74326-374">String</span></span>|  
|<span data-ttu-id="74326-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="74326-376">String</span><span class="sxs-lookup"><span data-stu-id="74326-376">String</span></span>|  
|<span data-ttu-id="74326-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="74326-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="74326-378">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-378">Int16</span></span>|  
|<span data-ttu-id="74326-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="74326-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="74326-380">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-380">Int16</span></span>|  
|<span data-ttu-id="74326-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="74326-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="74326-382">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-382">Int16</span></span>|  
|<span data-ttu-id="74326-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-383">REMARKS</span></span>|<span data-ttu-id="74326-384">String</span><span class="sxs-lookup"><span data-stu-id="74326-384">String</span></span>|  
|<span data-ttu-id="74326-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="74326-386">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="74326-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="74326-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="74326-388">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-388">ColumnName</span></span>|<span data-ttu-id="74326-389">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74326-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="74326-391">String</span><span class="sxs-lookup"><span data-stu-id="74326-391">String</span></span>|  
|<span data-ttu-id="74326-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74326-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="74326-393">String</span><span class="sxs-lookup"><span data-stu-id="74326-393">String</span></span>|  
|<span data-ttu-id="74326-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="74326-395">String</span><span class="sxs-lookup"><span data-stu-id="74326-395">String</span></span>|  
|<span data-ttu-id="74326-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-396">COLUMN_NAME</span></span>|<span data-ttu-id="74326-397">String</span><span class="sxs-lookup"><span data-stu-id="74326-397">String</span></span>|  
|<span data-ttu-id="74326-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-398">COLUMN_TYPE</span></span>|<span data-ttu-id="74326-399">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-399">Int16</span></span>|  
|<span data-ttu-id="74326-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-400">DATA_TYPE</span></span>|<span data-ttu-id="74326-401">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-401">Int16</span></span>|  
|<span data-ttu-id="74326-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-402">TYPE_NAME</span></span>|<span data-ttu-id="74326-403">String</span><span class="sxs-lookup"><span data-stu-id="74326-403">String</span></span>|  
|<span data-ttu-id="74326-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="74326-404">PRECISION</span></span>|<span data-ttu-id="74326-405">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-405">Int32</span></span>|  
|<span data-ttu-id="74326-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="74326-406">LENGTH</span></span>|<span data-ttu-id="74326-407">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-407">Int32</span></span>|  
|<span data-ttu-id="74326-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="74326-408">SCALE</span></span>|<span data-ttu-id="74326-409">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-409">Int16</span></span>|  
|<span data-ttu-id="74326-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="74326-410">RADIX</span></span>|<span data-ttu-id="74326-411">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-411">Int16</span></span>|  
|<span data-ttu-id="74326-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74326-412">NULLABLE</span></span>|<span data-ttu-id="74326-413">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-413">Int16</span></span>|  
|<span data-ttu-id="74326-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-414">REMARKS</span></span>|<span data-ttu-id="74326-415">String</span><span class="sxs-lookup"><span data-stu-id="74326-415">String</span></span>|  
|<span data-ttu-id="74326-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="74326-416">OVERLOAD</span></span>|<span data-ttu-id="74326-417">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-417">Int32</span></span>|  
|<span data-ttu-id="74326-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74326-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="74326-419">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="74326-420">Controlador ODBC de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="74326-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="74326-421">El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="74326-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="74326-422">Tablas</span><span class="sxs-lookup"><span data-stu-id="74326-422">Tables</span></span>  
  
-   <span data-ttu-id="74326-423">Índices</span><span class="sxs-lookup"><span data-stu-id="74326-423">Indexes</span></span>  
  
-   <span data-ttu-id="74326-424">Columnas</span><span class="sxs-lookup"><span data-stu-id="74326-424">Columns</span></span>  
  
-   <span data-ttu-id="74326-425">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="74326-425">Procedures</span></span>  
  
-   <span data-ttu-id="74326-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="74326-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="74326-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="74326-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="74326-428">Vistas</span><span class="sxs-lookup"><span data-stu-id="74326-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="74326-429">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="74326-429">Tables and Views</span></span>  
  
|<span data-ttu-id="74326-430">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-430">ColumnName</span></span>|<span data-ttu-id="74326-431">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74326-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="74326-433">String</span><span class="sxs-lookup"><span data-stu-id="74326-433">String</span></span>|  
|<span data-ttu-id="74326-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74326-434">TABLE_OWNER</span></span>|<span data-ttu-id="74326-435">String</span><span class="sxs-lookup"><span data-stu-id="74326-435">String</span></span>|  
|<span data-ttu-id="74326-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-436">TABLE_NAME</span></span>|<span data-ttu-id="74326-437">String</span><span class="sxs-lookup"><span data-stu-id="74326-437">String</span></span>|  
|<span data-ttu-id="74326-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-438">TABLE_TYPE</span></span>|<span data-ttu-id="74326-439">String</span><span class="sxs-lookup"><span data-stu-id="74326-439">String</span></span>|  
|<span data-ttu-id="74326-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-440">REMARKS</span></span>|<span data-ttu-id="74326-441">String</span><span class="sxs-lookup"><span data-stu-id="74326-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="74326-442">Columnas</span><span class="sxs-lookup"><span data-stu-id="74326-442">Columns</span></span>  
  
|<span data-ttu-id="74326-443">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-443">ColumnName</span></span>|<span data-ttu-id="74326-444">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74326-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="74326-446">String</span><span class="sxs-lookup"><span data-stu-id="74326-446">String</span></span>|  
|<span data-ttu-id="74326-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74326-447">TABLE_OWNER</span></span>|<span data-ttu-id="74326-448">String</span><span class="sxs-lookup"><span data-stu-id="74326-448">String</span></span>|  
|<span data-ttu-id="74326-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-449">TABLE_NAME</span></span>|<span data-ttu-id="74326-450">String</span><span class="sxs-lookup"><span data-stu-id="74326-450">String</span></span>|  
|<span data-ttu-id="74326-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-451">COLUMN_NAME</span></span>|<span data-ttu-id="74326-452">String</span><span class="sxs-lookup"><span data-stu-id="74326-452">String</span></span>|  
|<span data-ttu-id="74326-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-453">DATA_TYPE</span></span>|<span data-ttu-id="74326-454">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-454">Int16</span></span>|  
|<span data-ttu-id="74326-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-455">TYPE_NAME</span></span>|<span data-ttu-id="74326-456">String</span><span class="sxs-lookup"><span data-stu-id="74326-456">String</span></span>|  
|<span data-ttu-id="74326-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="74326-457">PRECISION</span></span>|<span data-ttu-id="74326-458">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-458">Int32</span></span>|  
|<span data-ttu-id="74326-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="74326-459">LENGTH</span></span>|<span data-ttu-id="74326-460">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-460">Int32</span></span>|  
|<span data-ttu-id="74326-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="74326-461">SCALE</span></span>|<span data-ttu-id="74326-462">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-462">Int16</span></span>|  
|<span data-ttu-id="74326-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="74326-463">RADIX</span></span>|<span data-ttu-id="74326-464">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-464">Int16</span></span>|  
|<span data-ttu-id="74326-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74326-465">NULLABLE</span></span>|<span data-ttu-id="74326-466">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-466">Int16</span></span>|  
|<span data-ttu-id="74326-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-467">REMARKS</span></span>|<span data-ttu-id="74326-468">String</span><span class="sxs-lookup"><span data-stu-id="74326-468">String</span></span>|  
|<span data-ttu-id="74326-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74326-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="74326-470">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="74326-471">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="74326-471">Procedures</span></span>  
  
|<span data-ttu-id="74326-472">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-472">ColumnName</span></span>|<span data-ttu-id="74326-473">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74326-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="74326-475">String</span><span class="sxs-lookup"><span data-stu-id="74326-475">String</span></span>|  
|<span data-ttu-id="74326-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74326-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="74326-477">String</span><span class="sxs-lookup"><span data-stu-id="74326-477">String</span></span>|  
|<span data-ttu-id="74326-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="74326-479">String</span><span class="sxs-lookup"><span data-stu-id="74326-479">String</span></span>|  
|<span data-ttu-id="74326-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="74326-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="74326-481">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-481">Int16</span></span>|  
|<span data-ttu-id="74326-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="74326-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="74326-483">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-483">Int16</span></span>|  
|<span data-ttu-id="74326-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="74326-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="74326-485">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-485">Int16</span></span>|  
|<span data-ttu-id="74326-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-486">REMARKS</span></span>|<span data-ttu-id="74326-487">String</span><span class="sxs-lookup"><span data-stu-id="74326-487">String</span></span>|  
|<span data-ttu-id="74326-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="74326-489">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="74326-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="74326-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="74326-491">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-491">ColumnName</span></span>|<span data-ttu-id="74326-492">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74326-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="74326-494">String</span><span class="sxs-lookup"><span data-stu-id="74326-494">String</span></span>|  
|<span data-ttu-id="74326-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74326-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="74326-496">String</span><span class="sxs-lookup"><span data-stu-id="74326-496">String</span></span>|  
|<span data-ttu-id="74326-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="74326-498">String</span><span class="sxs-lookup"><span data-stu-id="74326-498">String</span></span>|  
|<span data-ttu-id="74326-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-499">COLUMN_NAME</span></span>|<span data-ttu-id="74326-500">String</span><span class="sxs-lookup"><span data-stu-id="74326-500">String</span></span>|  
|<span data-ttu-id="74326-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-501">COLUMN_TYPE</span></span>|<span data-ttu-id="74326-502">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-502">Int16</span></span>|  
|<span data-ttu-id="74326-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-503">DATA_TYPE</span></span>|<span data-ttu-id="74326-504">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-504">Int16</span></span>|  
|<span data-ttu-id="74326-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-505">TYPE_NAME</span></span>|<span data-ttu-id="74326-506">String</span><span class="sxs-lookup"><span data-stu-id="74326-506">String</span></span>|  
|<span data-ttu-id="74326-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="74326-507">PRECISION</span></span>|<span data-ttu-id="74326-508">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-508">Int32</span></span>|  
|<span data-ttu-id="74326-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="74326-509">LENGTH</span></span>|<span data-ttu-id="74326-510">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-510">Int32</span></span>|  
|<span data-ttu-id="74326-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="74326-511">SCALE</span></span>|<span data-ttu-id="74326-512">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-512">Int16</span></span>|  
|<span data-ttu-id="74326-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="74326-513">RADIX</span></span>|<span data-ttu-id="74326-514">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-514">Int16</span></span>|  
|<span data-ttu-id="74326-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74326-515">NULLABLE</span></span>|<span data-ttu-id="74326-516">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-516">Int16</span></span>|  
|<span data-ttu-id="74326-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-517">REMARKS</span></span>|<span data-ttu-id="74326-518">String</span><span class="sxs-lookup"><span data-stu-id="74326-518">String</span></span>|  
|<span data-ttu-id="74326-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="74326-519">OVERLOAD</span></span>|<span data-ttu-id="74326-520">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-520">Int32</span></span>|  
|<span data-ttu-id="74326-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74326-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="74326-522">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="74326-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="74326-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="74326-524">ColumName</span><span class="sxs-lookup"><span data-stu-id="74326-524">ColumnName</span></span>|<span data-ttu-id="74326-525">DataType</span><span class="sxs-lookup"><span data-stu-id="74326-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74326-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="74326-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="74326-527">String</span><span class="sxs-lookup"><span data-stu-id="74326-527">String</span></span>|  
|<span data-ttu-id="74326-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74326-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="74326-529">String</span><span class="sxs-lookup"><span data-stu-id="74326-529">String</span></span>|  
|<span data-ttu-id="74326-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="74326-531">String</span><span class="sxs-lookup"><span data-stu-id="74326-531">String</span></span>|  
|<span data-ttu-id="74326-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-532">COLUMN_NAME</span></span>|<span data-ttu-id="74326-533">String</span><span class="sxs-lookup"><span data-stu-id="74326-533">String</span></span>|  
|<span data-ttu-id="74326-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-534">COLUMN_TYPE</span></span>|<span data-ttu-id="74326-535">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-535">Int16</span></span>|  
|<span data-ttu-id="74326-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-536">DATA_TYPE</span></span>|<span data-ttu-id="74326-537">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-537">Int16</span></span>|  
|<span data-ttu-id="74326-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74326-538">TYPE_NAME</span></span>|<span data-ttu-id="74326-539">String</span><span class="sxs-lookup"><span data-stu-id="74326-539">String</span></span>|  
|<span data-ttu-id="74326-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="74326-540">COLUMN_SIZE</span></span>|<span data-ttu-id="74326-541">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-541">Int32</span></span>|  
|<span data-ttu-id="74326-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74326-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="74326-543">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-543">Int32</span></span>|  
|<span data-ttu-id="74326-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="74326-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="74326-545">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-545">Int16</span></span>|  
|<span data-ttu-id="74326-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="74326-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="74326-547">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-547">Int16</span></span>|  
|<span data-ttu-id="74326-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74326-548">NULLABLE</span></span>|<span data-ttu-id="74326-549">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-549">Int16</span></span>|  
|<span data-ttu-id="74326-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74326-550">REMARKS</span></span>|<span data-ttu-id="74326-551">String</span><span class="sxs-lookup"><span data-stu-id="74326-551">String</span></span>|  
|<span data-ttu-id="74326-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="74326-552">COLUMN_DEF</span></span>|<span data-ttu-id="74326-553">String</span><span class="sxs-lookup"><span data-stu-id="74326-553">String</span></span>|  
|<span data-ttu-id="74326-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74326-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="74326-555">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-555">Int16</span></span>|  
|<span data-ttu-id="74326-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="74326-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="74326-557">Int16</span><span class="sxs-lookup"><span data-stu-id="74326-557">Int16</span></span>|  
|<span data-ttu-id="74326-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74326-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="74326-559">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-559">Int32</span></span>|  
|<span data-ttu-id="74326-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74326-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="74326-561">Int32</span><span class="sxs-lookup"><span data-stu-id="74326-561">Int32</span></span>|  
|<span data-ttu-id="74326-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74326-562">IS_NULLABLE</span></span>|<span data-ttu-id="74326-563">String</span><span class="sxs-lookup"><span data-stu-id="74326-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74326-564">Vea también</span><span class="sxs-lookup"><span data-stu-id="74326-564">See Also</span></span>  
 [<span data-ttu-id="74326-565">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="74326-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
