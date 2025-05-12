# Draw.io Diagram Prompt – Analysis & Improvements

## Original Prompt

```text
I would like to demonstrate the concept of diagrams-as-code to a class on genAI prompting that I'm teaching.  Specifically for this class, I want to demonstrate creating diagrams for the Draw.io diagramming tool (https://www.drawio.com/).  The reason for this selection is that the format to store diagrams in this tool is a very readable XML format.  I have created diagrams in dedicated diagrams-as-code languages like Mermaid.js and ArgoUML.  These work well, but are missing one aspect in their language specification which is sometimes needed: the ability to lay out diagram elements with a specified location within the diagram.  Draw.io does allow you to specify location, so I would like to demonstrate creating a diagram in this format with generative AI.
To quickly come up with a concept which could easily be diagrammed without much documentation, I'd like to create a data entity diagram for a commonly understood business model: a retail sales model.  Please create a basic entity diagram in an xml format which can be loaded directly into Draw.io for a retail sales business.  The model should include the following entities: invoices, line items, products, and customers - plus any additional entities you can think of which are related to this business model.  The diagram should be well laid out with no overlapping boxes and a minimum of overlapping connecting lines.  Before beginning, please let me know if you have any questions or need clarification.
```

## Portion‑by‑Portion Relevance & Benefit

### 1. Introduce teaching context and goal (`diagrams-as-code` for GenAI class)

*Benefit*: Gives the assistant awareness of audience and objective, allowing explanations and examples at a teaching‑friendly depth.

### 2. Specify target tool: **Draw.io** and link

*Benefit*: Constrains output format (Draw.io XML) and prevents assumptions about Mermaid or other DSLs.

### 3. Explain *why* Draw.io (readable XML, positional layout)

*Benefit*: Clarifies must‑have features (manual coordinates) and justifies tool choice so the assistant can lean on those capabilities.

### 4. State prior experience & limits of other tools (Mermaid, ArgoUML)

*Benefit*: Signals the assistant to skip suggesting those tools and focus on overcoming their positioning shortfall.

### 5. Describe feature requirement: ability to lay out elements by coordinates

*Benefit*: Tells the assistant to include `x`/`y` attributes for each node so the diagram appears tidy on import.

### 6. Choose an easy domain: **retail sales** entity model

*Benefit*: Keeps cognitive load low for students—everyone understands invoices, products, etc.

### 7. Explicit task: *create a basic entity diagram in Draw.io XML*

*Benefit*: Direct action item; no ambiguity about deliverable format.

### 8. List mandatory entities (invoices, line items, products, customers) plus 'any related'

*Benefit*: Ensures completeness while allowing creative additions (payments, inventory, etc.).

### 9. Layout requirements: *no overlapping boxes or excessive connector crossings*

*Benefit*: Drives assistant to set coordinates thoughtfully, improving immediate usability.

### 10. Invite clarification questions before starting

*Benefit*: Opens a feedback loop—critical for complex generation tasks to avoid rework.


## Potential Prompt Enhancements

- Add desired **styling guidance** (colors, rounded rectangles, fonts) to standardize the look across generated diagrams.
- Specify **relationship cardinalities** (e.g., one invoice *has many* line items) so the assistant can encode arrowheads or labels.
- Provide a **file name** and repository path (e.g., `retail_sales_entity.drawio`) to make the output immediately commit‑ready.
- Request **XML comments** (`<!-- ... -->`) above each node to help students map code to diagram parts.
- Include a **validation step** (“ensure the diagram imports without warnings”) to catch malformed XML before class.
- If time‑boxed, state an **expected generation time** to prevent lengthy waits during live demos.

## Example Refined Prompt

```markdown
**Refined Prompt for the Assistant**

You are ChatGPT assisting a GenAI‑prompting workshop.  
**Goal**: Generate a Draw.io XML file (`retail_sales_entity.drawio`) demonstrating *diagrams‑as‑code*.

**Requirements**
1. **Entities**: Customers, Invoices, Line Items, Products, Payments, Inventory  
2. **Relationships & Cardinalities**  
   - Customers 1‒* Invoices  
   - Invoices 1‒* Line Items  
   - Products 1‒* Line Items  
   - Payments 1‒1 Invoices  
3. **Layout**  
   - Explicit `x`,`y` coordinates; no overlapping nodes; minimal connector crossings.  
   - Use orthogonal connectors; apply distinct fill colours per entity type.  
4. **Annotations**: Insert `<!-- entity: Customers -->` XML comments before each node block.  
5. **Validation**: XML must import into Draw.io without warnings.

Ask clarifying questions before generating if any requirement is unclear.

```