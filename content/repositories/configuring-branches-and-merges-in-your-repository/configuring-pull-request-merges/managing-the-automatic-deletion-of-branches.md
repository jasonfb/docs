---
title: Managing the automatic deletion of branches
intro: You can have head branches automatically deleted after pull requests are merged in your repository.
redirect_from:
  - /articles/managing-the-automatic-deletion-of-branches
  - /github/administering-a-repository/managing-the-automatic-deletion-of-branches
  - /github/administering-a-repository/configuring-pull-request-merges/managing-the-automatic-deletion-of-branches
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Repositories
shortTitle: Automatic branch deletion
---
Anyone with admin permissions to a repository can enable or disable the automatic deletion of branches.

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
3. Under the **General** tab in the left sidebar, scroll down to the "Pull requests" section. There, select or unselect **Automatically delete head branches**.
  ![Checkbox to enable or disable automatic deletion of branches](https://user-images.githubusercontent.com/59002/189544276-02ed1e60-8cde-4e9f-981e-ef122ec655b6.png)
## Further reading
- "[Merging a pull request](/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request)"
- "[Creating and deleting branches within your repository](/articles/creating-and-deleting-branches-within-your-repository)"
