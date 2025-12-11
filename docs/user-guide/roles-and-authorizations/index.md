# Roles and authorizations

The following roles are available in the application:

*   Viewer
*   Operator
*   Editor
*   Administrator

They enable one to perform the below operations within the namespaces they contain access to.
Only a *Super-admin* user can create and delete a workspace (project) and grant initial access to this
project.

## Actions Table

| Role | Project Settings | Jobs | Pipelines |
| :--- | :--- | :--- | :--- |
| **Viewer** | View All | View All | View All |
| **Operator** | View All | View All / execute jobs | View All / execute pipelines |
| **Editor** | Edit All but Users/Roles | Edit / execute jobs | Edit / execute pipelines |
| **Admin** | Edit All | Edit / execute jobs | Edit / execute pipelines |