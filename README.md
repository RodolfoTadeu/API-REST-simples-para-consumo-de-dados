# API-REST 
<p>Esta API eu desenvolvi com base em um curso que eu fiz na udemy https://www.udemy.com/course/curso-de-javascript-moderno-do-basico-ao-avancado/</p>
<p>Para subir o projeto no ar com SQLite, copie o arquivo <code>.env_example</code>  para <code>.env</code> .</p>
<p> Você também precisará adicionar uma secret key no arquivo <code>.env</code>:</p>
<pre><code>TOKEN_SECRET='sua_secret_key_aqui'</code></pre>
<p>Execute os comandos abaixo:</p>
<pre><code>npm i
npx sequelize db:migrate
npx sequelize db:seed:all
npm run dev
</code>
</pre>
<p>Neste ponto sua API deverá está rodando no endereço <a href="http://127.0.0.1:3001/" rel="nofollow">http://127.0.0.1:3001/</a>.</p>
<p>Caso queira migrar para MySQL/MariaDB, edite as configurações de base de dados no arquivo <code>.env</code>, configure também o <code>src/config/database.js</code>.</p>
<p>Para SQLite as configurações são:</p>
<pre><p>require('dotenv').config();</p>
module.exports = {
  dialect: 'sqlite',
  storage: './db.sqlite',
  define: {
    timestamps: true,
    underscored: true,
    underscoredAll: true,
    createdAt: 'created_at',
    updatedAt: 'updated_at',
  },
};
</pre>
<p>Para MySQL/MariaDB as configurações são:</p>
<pre>
<p>require('dotenv').config();</p>

module.exports = {
  host: process.env.DATABASE_HOST,
  port: process.env.DATABASE_PORT,
  username: process.env.DATABASE_USERNAME,
  password: process.env.DATABASE_PASSWORD,
  database: process.env.DATABASE,
  dialectOptions: {
    timezone: 'America/Sao_Paulo',
  },
  timezone: 'America/Sao_Paulo',

  define: {
    timestamps: true,
    underscored: true,
    underscoredAll: true,
    createdAt: 'created_at',
    updatedAt: 'updated_at',
  },
};
</pre>
<p>As configurações começando com process.env. vem do arquivo .env.</p>
<p>Os dados de usuário e senha dos arquivos de seed são:</p>
<ul>
<li>email = <a href="mailto:admin@email.com">admin@email.com</a></li>
<li>senha = 123456</li>
</ul>
<p>Você pode obter o token JWT na rota <code>/tokens</code>, passando os dados JSON:</p>

<pre>{
	<span class="pl-s"><span class="pl-pds">"</span>email<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>admin@email.com<span class="pl-pds">"</span></span>,
	<span class="pl-s"><span class="pl-pds">"</span>password<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>123456<span class="pl-pds">"</span></span>
}</pre>

<p>Headers:</p>

<code>Content-Type	application/json; charset=utf-8</code>









