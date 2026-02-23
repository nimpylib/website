+++
date = '2025-01-03T21:04:15+08:00'
draft = false
title = 'home of NimPyLib'
description = 'Library to write Python in Nim'
keywords = ['Nim', 'Python', 'Library',  'nim-lang', 'pylib', 'meta-programming']
+++


***Write Python in [Nim][]!***

[Nim]: {{<url/nim>}}
[Python]: https://python.org

Python-like operators/functions and libraries as well as syntax sugars

in 
[<img alt=Nim src=img/nim_logo.svg height="7%" width="16%"></img>][Nim]

<details id="repo-list">
  <summary>children repos</summary>
  <ul id="repos"></ul>
</details>
<script>
const exclude_repos = ['.github',
  'template',
  'nimpylib', 'website'  // website is this website itself, nimpylib is the main repo
];
fetch('https://api.github.com/users/nimpylib/repos')
  .then(r => r.json())
  .then(data => {
    const ul = document.getElementById('repos');
    data.forEach(repo => {
      if (exclude_repos.includes(repo.name)) return;
      const li = document.createElement('li');
      const a = document.createElement('a');
      a.href = repo.html_url;
      a.textContent = repo.name;
      li.appendChild(a);
      ul.appendChild(li);
    });
  });
</script>

