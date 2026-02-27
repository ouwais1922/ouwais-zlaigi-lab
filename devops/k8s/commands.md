--dry-run:

| client              | server                    |
| ------------------- | ------------------------- |
| Local validation    | Real cluster validation   |
| No API call         | API server is contacted   |
| No RBAC check       | RBAC is checked           |
| No admission checks | Admission controllers run |
| Faster              | More realistic            |
