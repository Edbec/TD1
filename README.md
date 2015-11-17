# TD1
I. Git hub :                                                       
        - Authentification                                   
        - Système de pagination                                
        - Limitation de requêtes pour la page active                 
        - Fuseaux horaires actifs en fonction de la position de l'utilisateur                   
        - Gestion des erreurs                     
   Meteo :                                                                          
        - Récupérer les températures                      
        - Choix du format d'affichage des données              
        - Choix de la langue                                 
        - Ciblage de ville par recherche                        
        - Ciblage de ville par géolocalisation                       
        
II. - Git hub : *GET + GET /user/repos + GET /repos/:owner/:repo + GET /users/:username/repos + GET /orgs/:org/repos + GET /repositories + GET /repos/:owner/:repo/contributors + GET /repos/:owner/:repo/languages + GET /repos/:owner/:repo/teams + GET /repos/:owner/:repo/branches + GET /repos/:owner/:repo/branches/:branch

    *POST
        + POST /user/repos
        + POST /orgs/:org/repos

    *Authentifié (token)
        + $ curl -H "Authorization: token OAUTH-TOKEN" https://api.github.com (à envoyer dans le header)
        + $ curl https://api.github.com/?access_token=OAUTH-TOKEN ( à envoyer en tant que paramètres)
        
III. Test des requêtes avec Postman, dans les deux cas on utilise la commande HTTP GET :

Test de la requête user :
    "login": "mojombo",
    "id": 1,
    "avatar_url": "https://avatars.githubusercontent.com/u/1?v=3",
    "gravatar_id": "",
    "url": "https://api.github.com/users/mojombo",
    "html_url": "https://github.com/mojombo",
    "followers_url": "https://api.github.com/users/mojombo/followers",
    "following_url": "https://api.github.com/users/mojombo/following{/other_user}",
    "gists_url": "https://api.github.com/users/mojombo/gists{/gist_id}",
    "starred_url": "https://api.github.com/users/mojombo/starred{/owner}{/repo}",
    "subscriptions_url": "https://api.github.com/users/mojombo/subscriptions",
    "organizations_url": "https://api.github.com/users/mojombo/orgs",
    "repos_url": "https://api.github.com/users/mojombo/repos",
    "events_url": "https://api.github.com/users/mojombo/events{/privacy}",
    "received_events_url": "https://api.github.com/users/mojombo/received_events",
    "type": "User",
    "site_admin": false

Ces informations concernent le premier utilisateur inscrit sur le site.

Test de la requête repositories : 
     Même structure et informations que précédemment, avec en plus: 

    "private": false,
    "html_url": "https://github.com/mojombo/grit",
    "description": "**Grit is no longer maintained. Check out libgit2/rugged.** Grit gives you object oriented read/write access to Git repositories via Ruby.",
    "fork": false,
    "url": "https://api.github.com/repos/mojombo/grit",
    "forks_url": "https://api.github.com/repos/mojombo/grit/forks",
    "keys_url": "https://api.github.com/repos/mojombo/grit/keys{/key_id}",
    "collaborators_url": "https://api.github.com/repos/mojombo/grit/collaborators{/collaborator}",
    "teams_url": "https://api.github.com/repos/mojombo/grit/teams",
    "hooks_url": "https://api.github.com/repos/mojombo/grit/hooks",
    "issue_events_url": "https://api.github.com/repos/mojombo/grit/issues/events{/number}",
    "events_url": "https://api.github.com/repos/mojombo/grit/events",
    "assignees_url": "https://api.github.com/repos/mojombo/grit/assignees{/user}",
    "branches_url": "https://api.github.com/repos/mojombo/grit/branches{/branch}",
    "tags_url": "https://api.github.com/repos/mojombo/grit/tags",
    "blobs_url": "https://api.github.com/repos/mojombo/grit/git/blobs{/sha}",
    "git_tags_url": "https://api.github.com/repos/mojombo/grit/git/tags{/sha}",
    "git_refs_url": "https://api.github.com/repos/mojombo/grit/git/refs{/sha}",
    "trees_url": "https://api.github.com/repos/mojombo/grit/git/trees{/sha}",
    "statuses_url": "https://api.github.com/repos/mojombo/grit/statuses/{sha}",
    "languages_url": "https://api.github.com/repos/mojombo/grit/languages",
    "stargazers_url": "https://api.github.com/repos/mojombo/grit/stargazers",
    "contributors_url": "https://api.github.com/repos/mojombo/grit/contributors",
    "subscribers_url": "https://api.github.com/repos/mojombo/grit/subscribers",
    "subscription_url": "https://api.github.com/repos/mojombo/grit/subscription",
    "commits_url": "https://api.github.com/repos/mojombo/grit/commits{/sha}",
    "git_commits_url": "https://api.github.com/repos/mojombo/grit/git/commits{/sha}",
    "comments_url": "https://api.github.com/repos/mojombo/grit/comments{/number}",
    "issue_comment_url": "https://api.github.com/repos/mojombo/grit/issues/comments{/number}",
    "contents_url": "https://api.github.com/repos/mojombo/grit/contents/{+path}",
    "compare_url": "https://api.github.com/repos/mojombo/grit/compare/{base}...{head}",
    "merges_url": "https://api.github.com/repos/mojombo/grit/merges",
    "archive_url": "https://api.github.com/repos/mojombo/grit/{archive_format}{/ref}",
    "downloads_url": "https://api.github.com/repos/mojombo/grit/downloads",
    "issues_url": "https://api.github.com/repos/mojombo/grit/issues{/number}",
    "pulls_url": "https://api.github.com/repos/mojombo/grit/pulls{/number}",
    "milestones_url": "https://api.github.com/repos/mojombo/grit/milestones{/number}",
    "notifications_url": "https://api.github.com/repos/mojombo/grit/notifications{?since,all,participating}",
    "labels_url": "https://api.github.com/repos/mojombo/grit/labels{/name}",
    "releases_url": "https://api.github.com/repos/mojombo/grit/releases{/id}"
    On retrouve donc les informations sur le premier dépôt qui a été effectué sur GitHub. 
    
                                                                                                           
IV. Liste des fonctionnalités pour la requête GET users :               
        - Afficher un utilisateur spécifique (en utilisant son pseudo)           
        - Afficher un utilisateur authentifié                                       
        - Afficher tout les utilisateurs                                                 
   Liste des fonctionnalités pour la requête GET repositories :                             
        - Afficher mes répertoires                                                                
        - Afficher le répertoire d'un utilisateur                                            
        - Affiher les répertoires d'un utilisateur spécifique (en utilisant son pseudo)                   
        - Afficher l'organisation des répertoires                                                    
        - Afficher tout les répertoires public                                                          
   Liste des fonctionnalités qu'on ne retrouve que sur la version web :                               
        - Afficher la liste des contributeurs d'un répertoire d'un utilisateur                         
        - Afficher la liste des langues d'un répertoire d'un utilisateur                                            
        - Afficher les équipes d'un répertoire d'un utilisateur                                     
        - Afficher les tags d'un répertoire d'un utilisateur                                               
