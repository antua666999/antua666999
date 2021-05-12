{
	"version": "2",
	"templates": [
		{
			"categories": [
				"Music"
			],
			"description": "Airsonic is a free, web-based media streamer, providing ubiqutious access to your music. Use it to share your music with friends, or to listen to your own music while at work. You can stream to multiple players simultaneously, for instance to one player in your kitchen and another in your living room.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "CONTEXT_PATH",
					"name": "CONTEXT_PATH",
					"set": "airsonic"
				},
				{
					"label": "JAVA_OPTS",
					"name": "JAVA_OPTS",
					"set": "-Xms256m -Xmx512m"
				}
			],
			"image": "linuxserver/airsonic:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/airsonic-logo.png",
			"name": "airsonic",
			"platform": "linux",
			"ports": [
				"4040:4040/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Airsonic",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Music",
					"container": "/music"
				},
				{
					"bind": "/portainer/Files/AppData/Airsonic/Playlists",
					"container": "/playlists"
				},
				{
					"bind": "/portainer/Podcasts",
					"container": "/podcasts"
				},
				{
					"bind": "/portainer/Files/AppData/Airsonic/Media",
					"container": "/media"
				},
				{
					"bind": "/portainer/Files/AppData/Config/Airsonic/",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools",
				"Authentication"
			],
			"description": "An open-source authentication and authorization server providing 2-factor authentication and single sign-on (SSO) for your applications via a web portal.",
			"env": [
				{
					"label": "TZ",
					"name": "TZ"
				}
			],
			"image": "authelia/authelia:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/authelia.png",
			"name": "authelia",
			"note": "Requires a configuration.yml file in order to work. Documentation is Available \u003ca href='https://docs.authelia.com/deployment/deployment-ha'\u003ehere\u003c/a\u003e.",
			"platform": "linux",
			"ports": [
				"9091:9091/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Authelia",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Authelia",
					"container": "/etc/authelia/"
				}
			]
		},
		{
			"categories": [
				"Video",
				"Music"
			],
			"description": "Bazarr is a companion application to Sonarr and Radarr. It can manage and download subtitles based on your requirements. You define your preferences by TV show or movie and Bazarr takes care of everything for you.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "TZ",
					"name": "TZ"
				}
			],
			"image": "linuxserver/bazarr:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/bazarr.png",
			"name": "bazarr",
			"platform": "linux",
			"ports": [
				"6767:6767/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Bazarr",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Bazarr",
					"container": "/config"
				},
				{
					"bind": "/portainer/TV",
					"container": "/tv"
				},
				{
					"bind": "/portainer/Movies",
					"container": "/movies"
				}
			]
		},
		{
			"categories": [
				"Music"
			],
			"description": "The purpose of beets is to get your music collection right once and for all. It catalogs your collection, automatically improving its metadata as it goes using the MusicBrainz database. Then it provides a bouquet of tools for manipulating and accessing your music.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/beets:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/beets-icon.png",
			"name": "beets",
			"platform": "linux",
			"ports": [
				"8337:8337/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Beets",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Beets",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				},
				{
					"bind": "/portainer/Music",
					"container": "/music"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "This is a Bitwarden server API implementation written in Rust compatible with upstream Bitwarden clients*, perfect for self-hosted deployment where running the official resource-heavy service might not be ideal..",
			"image": "bitwardenrs/server:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/bitwarden.png",
			"name": "bitwardenrs",
			"note": "This project is not associated with the Bitwarden project nor 8bit Solutions LLC.",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Bitwarden RS",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Bitwarden-rs",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Books",
				"Other"
			],
			"description": "Booksonic is a server and an app for streaming your audiobooks to any pc or android phone. Most of the functionality is also availiable on other platforms that have apps for subsonic",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"default": "booksonic",
					"label": "CONTEXT_PATH",
					"name": "CONTEXT_PATH"
				}
			],
			"image": "linuxserver/booksonic:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/booksonic.png",
			"name": "booksonic",
			"platform": "linux",
			"ports": [
				"4040:4040/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Booksonic",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Books",
					"container": "/books"
				},
				{
					"bind": "/portainer/Files/Podcasts",
					"container": "/podcast"
				},
				{
					"bind": "/portainer/Files/AppData/Config/Booksonic",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "Embystat is a personal web server that can calculate all kinds of statistics from your (local) Emby server. Just install this on your server and let him calculate all kinds of fun stuff.",
			"image": "linuxserver/embystat:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/embystat.png",
			"name": "embystat",
			"note": "Access the ui at your-ip:6555. Follow the setup wizard on initial install. Then configure the required services.",
			"platform": "linux",
			"ports": [
				"6555:6555/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "EmbyStat",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/EmbyStat",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Music"
			],
			"description": null,
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/headphones:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/headphones-icon.png",
			"name": "headphones",
			"platform": "linux",
			"ports": [
				"8181:8181/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Headphones",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Headphones",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/Downloads"
				},
				{
					"bind": "/portainer/Music",
					"container": "/music"
				}
			]
		},
		{
			"categories": [
				"Tools",
				"Web",
				"Other"
			],
			"description": "Heimdall is a way to organise all those links to your most used web sites and web applications in a simple way.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/heimdall:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/heimdall-icon.png",
			"name": "heimdall",
			"platform": "linux",
			"ports": [
				"80/tcp",
				"443/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Heimdall",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Heimdall",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "A dead simple static HOMepage for your servER to keep your s ervices on hand, from a simple yaml configuration file.",
			"image": "b4bz/homer:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/homer.png",
			"name": "homer",
			"note": "This container requires a yml file within the config volume. See the documentation here https://github.com/bastienwirtz/homer",
			"platform": "linux",
			"ports": [
				"8902:8080/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Homer",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Homer/assets",
					"container": "/www/assets"
				},
				{
					"bind": "/portainer/Files/AppData/Config/Homer",
					"container": "/www/config.yml"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "Create agents that monitor and act on your behalf.",
			"image": "huginn/huginn:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/huginn.png",
			"name": "huginn",
			"platform": "linux",
			"ports": [
				"3000:3000/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Huginn",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/huginn",
					"container": "/var/lib/mysql"
				}
			]
		},
		{
			"categories": [
				"Cloud",
				"Productivity",
				"Tools",
				"Other",
				"Web"
			],
			"description": "Invoices, Expenses and Tasks built with Laravel and Flutter.",
			"env": [
				{
					"default": "invoice.my.domain",
					"label": "URL",
					"name": "URL"
				},
				{
					"label": "APP_KEY",
					"name": "APP_KEY"
				},
				{
					"label": "TZ",
					"name": "TZ"
				},
				{
					"label": "DATABASE_PASSWORD",
					"name": "DATABASE_PASSWORD"
				},
				{
					"label": "MYSQL_ROOT_PASSWORD",
					"name": "MYSQL_ROOT_PASSWORD"
				},
				{
					"label": "PORT",
					"name": "PORT"
				}
			],
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/invoice_ninja.png",
			"name": "invoice_ninja",
			"note": "The database user is invoice_ninja and the database is ninja_db. Please generate an app key following the documentation \u003ca href='https://github.com/invoiceninja/dockerfiles'\u003ehere\u003c/a\u003e. ",
			"platform": "linux",
			"repository": {
				"stackfile": "Template/Stack/invoice-ninja.yml",
				"url": "https://github.com/SelfhostedPro/selfhosted_templates"
			},
			"title": "Invoice Ninja",
			"type": 3
		},
		{
			"categories": [
				"Downloaders",
				"Tools"
			],
			"description": "Jackett works as a proxy server it translates queries from apps like Sonarr etc into tracker-site-specific http queries and parses the html response sending results back to the requesting software.[",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/jackett:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/jacket-icon.png",
			"name": "jackett",
			"platform": "linux",
			"ports": [
				"9117:9117/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Jackett",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Jackett",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				}
			]
		},
		{
			"categories": [
				"Video",
				"Music",
				"Photos"
			],
			"description": "Jellyfin is a Free Software Media System that puts you in control of managing and streaming your media. It is an alternative to the proprietary Emby and Plex, to provide media from a dedicated server to end-user devices via multiple apps.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "TZ",
					"name": "TZ"
				}
			],
			"image": "linuxserver/jellyfin:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/jellyfin.png",
			"name": "jellyfin",
			"platform": "linux",
			"ports": [
				"8096:8096/tcp",
				"8920:8920/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Jellyfin",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Jellyfin",
					"container": "/config"
				},
				{
					"bind": "/portainer/TV",
					"container": "/data/tvshows"
				},
				{
					"bind": "/portainer/Movies",
					"container": "/data/movies"
				}
			]
		},
		{
			"categories": [
				"Video"
			],
			"description": "Headless installation of Kodi™ (formerly known as XBMC™), to enable library updates.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/kodi-headless:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/kodi-icon.png",
			"name": "kodi-headless",
			"platform": "linux",
			"ports": [
				"8080/tcp",
				"9777/udp"
			],
			"restart_policy": "unless-stopped",
			"title": "Kodi Headless",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Kodi",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Books"
			],
			"description": "LazyLibrarian is a program to follow authors and grab metadata for all your digital reading needs.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/lazylibrarian:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/lazylibrarian-icon.png",
			"name": "lazylibrarian",
			"platform": "linux",
			"ports": [
				"5299:5299/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "LazyLibrarian",
			"type": 1,
			"volumes": [
				{
					"container": "/config"
				},
				{
					"container": "/downloads"
				},
				{
					"container": "/books"
				}
			]
		},
		{
			"categories": [
				"Tools",
				"Web"
			],
			"description": "This container sets up an Nginx webserver and reverse proxy with php support and a built-in letsencrypt client that automates free SSL server certificate generation and renewal processes. It also contains fail2ban for intrusion prevention.\r\n  \r\n  Before running this container, make sure that the url and subdomains are properly forwarded to this container's host.\r\n  \r\n  - Port 443 on the internet side of the router should be forwarded to this container's port 443.\r\n  - If you need a dynamic dns provider, you can use the free provider duckdns.org where the url will be yoursubdomain.duckdns.org and the subdomains    can be www,ftp,cloud\r\n  - The container detects changes to url and subdomains, revokes existing certs and generates new ones during start. \r\n  - It also detects changes to the DHLEVEL parameter and replaces the dhparams file.\r\n  \r\n  - If you'd like to password protect your sites, you can use htpasswd. Run the following command on your host to generate the htpasswd file docker exec -it letsencrypt htpasswd -c /config/nginx/.htpasswd \u0026lt;username\u0026gt;",
			"env": [
				{
					"label": "EMAIL",
					"name": "EMAIL",
					"set": "-Xms256m -Xmx512m"
				},
				{
					"label": "URL",
					"name": "URL",
					"set": "-Xms256m -Xmx512m"
				},
				{
					"label": "SUBDOMAINS",
					"name": "SUBDOMAINS",
					"set": "www,"
				},
				{
					"label": "ONLY_SUBDOMAINS",
					"name": "ONLY_SUBDOMAINS",
					"set": "false"
				},
				{
					"label": "DHLEVEL",
					"name": "DHLEVEL",
					"set": "2048"
				},
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "VALIDATION",
					"name": "VALIDATION",
					"set": "http"
				},
				{
					"label": "DNSPLUGIN",
					"name": "DNSPLUGIN",
					"set": "http"
				}
			],
			"image": "linuxserver/letsencrypt:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/letsencrypt.png",
			"name": "letsencrypt",
			"platform": "linux",
			"ports": [
				"80/tcp",
				"443/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Let's Encrypt",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/LetsEncrypt",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "A Free and Open Source Speedtest for HTML5 and more.",
			"image": "linuxserver/librespeed:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/speedtest.png",
			"name": "librespeed",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "LibreSpeed",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/LibreSpeed",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Cloud",
				"Web",
				"Management",
				"Photos"
			],
			"description": "Lychee is a free photo-management tool, which runs on your server or web-space. Installing is a matter of seconds. Upload, manage and share photos like from a native application. Lychee comes with everything you need and all your photos are stored securely.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/lychee:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/lychee-icon.png",
			"name": "lychee",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Lychee",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Lychee",
					"container": "/config"
				},
				{
					"bind": "/portainer/Pictures",
					"container": "/pictures"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "An Enhanced drop in replacement for Mysql",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "MYSQL_ROOT_PASSWORD",
					"name": "MYSQL_ROOT_PASSWORD",
					"set": ""
				}
			],
			"image": "linuxserver/mariadb:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/mariadb-icon.png",
			"name": "mariadb",
			"platform": "linux",
			"ports": [
				"3306:3306/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "MariaDB",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Mariadb",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other"
			],
			"description": "McMyAdmin 2 is the leading web control panel and administration console for Minecraft servers.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/mcmyadmin2:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/mcmyadmin-icon.png",
			"name": "mcmyadmin2",
			"platform": "linux",
			"ports": [
				"8080:8080/tcp",
				"25565:25565/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "McMyAdmin 2",
			"type": 1,
			"volumes": [
				{
					"container": "/minecraft"
				}
			]
		},
		{
			"categories": [
				"Downloaders",
				"Video"
			],
			"description": "Medusa, automatic Video Library Manager for TV Shows. It watches for new episodes of your favorite shows, and when they are posted it does its magic.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/medusa:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/medusa-icon.png",
			"name": "medusa",
			"platform": "linux",
			"ports": [
				"8081:8081/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Medusa",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Medusa",
					"container": "/config"
				},
				{
					"bind": "/portainer/TV",
					"container": "/tv"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				}
			]
		},
		{
			"categories": [
				"Other"
			],
			"description": "Server version of minetest, a free, open source alternative to minecraft.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/minetest:latest",
			"logo": "https://raw.githubusercontent.com/linuxserver/beta-templates/master/lsiodev/img/minetest-icon.png",
			"name": "minetest",
			"platform": "linux",
			"ports": [
				"30000:30000/udp"
			],
			"restart_policy": "unless-stopped",
			"title": "Minetest",
			"type": 1,
			"volumes": [
				{
					"container": "/config/.minetest"
				}
			]
		},
		{
			"categories": [
				"Video",
				"Other",
				"Tools"
			],
			"description": "Minisatip is a multi-threaded satip server version 1.2 that runs under Linux and it was tested with DVB-S, DVB-S2, DVB-T, DVB-T2, DVB-C, DVB-C2, ATSC and ISDB-T cards.\n\n  The application is designed to stream the requested data to multiple clients (even with one dvb card) at the same time while opening different pids.\n  ",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/minisatip:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/minisatip-icon.png",
			"name": "minisatip",
			"platform": "linux",
			"ports": [
				"8875:8875/tcp",
				"554:554/tcp",
				"1900:1900/udp"
			],
			"restart_policy": "unless-stopped",
			"title": "Minisatip",
			"type": 1
		},
		{
			"categories": [
				"Other",
				"Music"
			],
			"description": "Mstream is a personal music streaming server. You can use mStream to stream your music from your home computer to any device, anywhere. There are mobile apps available for both Android and iPhone..",
			"image": "linuxserver/mstream:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/mstream.png",
			"name": "mstream",
			"platform": "linux",
			"ports": [
				"3000:3000/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Mstream",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Mstream",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/music"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Voice",
				"Chat"
			],
			"description": "Mumble is a voicechat program for gamers written on top of Qt and Opus. Murmur is the server backend for Mumble.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "TZ",
					"name": "TZ"
				}
			],
			"image": "goofball222/murmur:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/Mumble-logo.png",
			"name": "murmur",
			"platform": "linux",
			"ports": [
				"64738:64738/tcp",
				"64738:64738/udp"
			],
			"restart_policy": "unless-stopped",
			"title": "Murmur",
			"type": 1,
			"volumes": [
				{
					"bind": "/etc/localtime:ro",
					"container": "/etc/localtime"
				},
				{
					"bind": "/portainer/Files/Config/Murmur",
					"container": "/opt/murmur/config"
				},
				{
					"bind": "/portainer/Files/Murmur/data",
					"container": "/opt/murmur/data"
				},
				{
					"bind": "/portainer/Files/Murmur/log",
					"container": "/opt/murmur/log"
				}
			]
		},
		{
			"categories": [
				"Music",
				"Other",
				"Tools"
			],
			"description": " MusicBrainz is an open music encyclopedia that collects music metadata and makes it available to the public.",
			"env": [
				{
					"label": "BRAINZCODE",
					"name": "BRAINZCODE",
					"set": ""
				},
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/musicbrainz:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/musicbrainz-icon.png",
			"name": "musicbrainz",
			"platform": "linux",
			"ports": [
				"5000:5000/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "MusicBrainz",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/MusicBrainz",
					"container": "/config"
				},
				{
					"bind": "/portainer/Files/AppData/MusicBrainz",
					"container": "/data"
				}
			]
		},
		{
			"categories": [
				"Web",
				"Proxy",
				"Other",
				"Tools"
			],
			"description": "A lightweight portal to view, manage your HTPC apps without having to run anything more than a PHP enabled webserver. With Muximux you don't need to keep multiple tabs open, or bookmark the URL to all of your apps.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/muximux:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/muximux-icon.png",
			"name": "muximux",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Muximux",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Muximux",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Downloaders",
				"Books"
			],
			"description": "An automated Comic Book downloader (cbr/cbz) for use with SABnzbd, NZBGet and torrents.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/mylar:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/mylar-icon.png",
			"name": "mylar",
			"platform": "linux",
			"ports": [
				"8090:8090/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Mylar",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Mylar",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				},
				{
					"bind": "/portainer/Comics",
					"container": "/comics"
				}
			]
		},
		{
			"categories": [
				"Cloud",
				"Productivity",
				"Tools",
				"Other",
				"Web"
			],
			"description": "Where are your photos and documents? With Nextcloud you pick a server of your choice, at home, in a data center or at a provider. And that is where your files will be. Nextcloud runs on that server, protecting your data and giving you access from your desktop or mobile devices.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "TZ",
					"name": "TZ"
				},
				{
					"label": "DATABASE_PASSWORD",
					"name": "DATABASE_PASSWORD"
				},
				{
					"label": "MYSQL_ROOT_PASSWORD",
					"name": "MYSQL_ROOT_PASSWORD"
				},
				{
					"label": "PORT",
					"name": "PORT"
				}
			],
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/nextcloud-icon.png",
			"name": "nextcloud",
			"note": "The database user is nextcloud and the database is nextcloud_db. The host of the database will be located at the bottom of the DB conotainer in portainer.",
			"platform": "linux",
			"repository": {
				"stackfile": "Template/Stack/nextcloud.yml",
				"url": "https://github.com/SelfhostedPro/selfhosted_templates"
			},
			"title": "Nextcloud",
			"type": 3
		},
		{
			"categories": [
				"Web",
				"Proxy"
			],
			"description": "Nginx is a web server with a strong focus on high concurrency, performance and low memory usage. It can also act as a reverse proxy server for HTTP, HTTPS, SMTP, POP3, and IMAP protocols, as well as a load balancer and an HTTP cache.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/nginx:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/nginx-icon.png",
			"name": "nginx",
			"platform": "linux",
			"ports": [
				"80/tcp",
				"443/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Nginx",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Nginx",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Proxy",
				"Tools"
			],
			"description": "Nginx Proxy Manager enables you to easily forward to your websites running at home or otherwise, including free SSL, without having to know too much about Nginx or Letsencrypt.",
			"image": "jlesage/nginx-proxy-manager",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/proxy_mgr.png",
			"name": "nginx-proxy-manager",
			"platform": "linux",
			"ports": [
				"80:8080/tcp",
				"81:8181/tcp",
				"443:4443/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Nginx Proxy Manager",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Nginx-Proxy",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Downloaders"
			],
			"description": "NZBGet is a usenet downloader, written in C++ and designed with performance in mind to achieve maximum download speed by using very little system resources. It supports all platforms including Windows, Mac, Linux and works on all devices including PC, NAS, WLAN routers and media players",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/nzbget:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/nzbget-icon.png",
			"name": "nzbget",
			"platform": "linux",
			"ports": [
				"6789:6789/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "NZBGet",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Nzbget",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				}
			]
		},
		{
			"categories": [
				"Downloaders",
				"Other",
				"Tools"
			],
			"description": "NZBHydra is a meta search for NZB indexers and the \"spiritual successor\" to NZBmegasearcH. It provides easy access to a number of raw and newznab based indexers.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/nzbhydra2:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/hydra-icon.png",
			"name": "nzbhydra2",
			"platform": "linux",
			"ports": [
				"5076:5076/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "NZBHydra 2",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Nzbhydra2",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				}
			]
		},
		{
			"categories": [
				"Downloaders",
				"Other",
				"Video",
				"Tools"
			],
			"description": "Ombi allows you to host your own Plex Request and user management system. ",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/ombi:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/ombi.png",
			"name": "ombi",
			"platform": "linux",
			"ports": [
				"3579:3579/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Ombi",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Ombi",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other"
			],
			"description": "OpenVPN Access Server is a full featured secure network tunneling VPN software solution that integrates OpenVPN server capabilities, enterprise management capabilities, simplified OpenVPN Connect UI, and OpenVPN Client software packages that accommodate Windows, MAC, Linux, Android, and iOS environments.",
			"env": [
				{
					"label": "INTERFACE",
					"name": "INTERFACE",
					"set": "eth0"
				},
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/openvpn-as:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/openvpn-as-icon.png",
			"name": "openvpn-as",
			"platform": "linux",
			"ports": [
				"943:943/tcp",
				"9443:9443/tcp",
				"1194:1194/udp"
			],
			"restart_policy": "unless-stopped",
			"title": "OpenVPN Access Server",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/OpenVPN-AS",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "Organizr allows you to setup Tabs that will be loaded all in one webpage. You can then work on your server with ease.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "organizrtools/organizr-v2:php-fpm",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/organizr-icon.png",
			"name": "organizr-v2",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Organizr v2",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Organizr",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other"
			],
			"description": "OScam is a softcam, software to be used to decrypt digital television channels on a settopbox (receiver), as an alternative for a conditional access module\n  (CAM). OScam is, compared with other softcams (CCcam, mgcamd, etc.), open source. Hence, the name Open Source Conditional Access Module (OScam). OScam is based on the\n  not so well known softcam MpCS. The main features of OSCam are next to its softcam capabilities, that it is able to function as a cardserver.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/oscam:latest",
			"logo": "http://i.imgur.com/8LadrLg.png",
			"name": "oscam",
			"platform": "linux",
			"ports": [
				"8888:8888/tcp",
				"10000:10000/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "OScam",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/OScam",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Photos"
			],
			"description": "A simple, easy way to turn a photo album into a webgallery",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/photoshow:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/photoshow-icon.png",
			"name": "photoshow",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "PhotoShow",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Pictures",
					"container": "/Pictures"
				},
				{
					"bind": "/portainer/Files/AppData/Photoshow/Thumbs",
					"container": "/Thumbs"
				},
				{
					"bind": "/portainer/Files/AppData/Config/PhotoShow",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "Self-hosted snippet manager.",
			"image": "snowmean/snibox-sqlite:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/snibox.png",
			"name": "snibox",
			"note": "Label-oriented interface with search. Supports various programming languages, markdown, plain text.",
			"platform": "linux",
			"ports": [
				"3010:3000/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Snibox",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Snibox",
					"container": "/app/db/database"
				}
			]
		},
		{
			"categories": [
				"Wiki"
			],
			"description": "Bookstack is a free and open source Wiki designed for creating beautiful documentation. Feautring a simple, but powerful WYSIWYG editor it allows for teams to create detailed and useful documentation with ease.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "TZ",
					"name": "TZ"
				},
				{
					"label": "DATABASE_PASSWORD",
					"name": "DATABASE_PASSWORD"
				},
				{
					"label": "MYSQL_ROOT_PASSWORD",
					"name": "MYSQL_ROOT_PASSWORD"
				},
				{
					"label": "PORT",
					"name": "PORT"
				}
			],
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/bookstack2.png",
			"note": "Default login is admin@admin.com with a password of password. The database created is called bookstackapp and the database user is called bookstack",
			"platform": "linux",
			"repository": {
				"stackfile": "Template/Stack/bookstack.yml",
				"url": "https://github.com/SelfhostedPro/selfhosted_templates"
			},
			"title": "Bookstack",
			"type": 3
		},
		{
			"categories": [
				"Other",
				"Tools",
				"Photo"
			],
			"description": "Chevereto is a powerful and fast image hosting script that allows you to create your very own full featured image hosting website in just minutes. Please note that this offers only the free Chevereto version..",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "CHEVERETO_DB_HOST",
					"name": "CHEVERETO_DB_HOST",
					"set": ""
				},
				{
					"label": "CHEVERETO_DB_USERNAME",
					"name": "CHEVERETO_DB_USERNAME",
					"set": ""
				},
				{
					"label": "CHEVERETO_DB_PASSWORD",
					"name": "CHEVERETO_DB_PASSWORD",
					"set": ""
				},
				{
					"label": "CHEVERETO_DB_NAME",
					"name": "CHEVERETO_DB_NAME",
					"set": ""
				},
				{
					"label": "CHEVERETO_DB_PREFIX",
					"name": "CHEVERETO_DB_PREFIX",
					"set": ""
				}
			],
			"image": "nmtan/chevereto:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/Chevereto.png",
			"name": "Chevereto",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Chevereto",
			"type": 1,
			"volumes": [
				{
					"container": "/var/www/html/images"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "Save recipes in seconds with plain text formatting and create beatiful recipe pages with automated ease.",
			"image": "gregyankovoy/chowdown:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/chowdown.png",
			"name": "Chowdown",
			"platform": "linux",
			"ports": [
				"4000:4000/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Chowdown",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Chowdown",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Cloud",
				"Books"
			],
			"description": "Calibre Web is a web app providing a clean interface for browsing, reading and downloading eBooks using an existing Calibre database.\n\n  [br][br]\n  [b][u][span style='color: #E80000;']Configuration[/span][/u][/b][br]\n  [b]/config[/b] Where Calibre-web should store it's database[br]\n  [b]/books[/b] Path to your calibre library metadata.db file[br]",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/calibre-web:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/calibre-web-icon.png",
			"name": "calibre-web",
			"platform": "linux",
			"ports": [
				"8083:8083/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Calibre Web",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Books",
					"container": "/books"
				},
				{
					"bind": "/portainer/Files/AppData/Config/Calibre-web",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Downloaders"
			],
			"description": "Cardigann, a server for adding extra indexers to Sonarr, SickRage and CouchPotato via Torznab and TorrentPotato proxies. Behind the scenes Cardigann logs in and runs searches and then transforms the results into a compatible format.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/cardigann:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/cardigann.png",
			"name": "cardigann",
			"platform": "linux",
			"ports": [
				"5060:5060/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Cardigann",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Cardigann",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "Code-server is VS Code running on a remote server, accessible through the browser.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "1000",
					"label": "PUID",
					"name": "GUID"
				},
				{
					"label": "TZ",
					"name": "TZ"
				},
				{
					"label": "PASSWORD",
					"name": "PASSWORD"
				},
				{
					"label": "SUDO_PASSWORD",
					"name": "SUDO_PASSWORD"
				},
				{
					"default": "example.my.domain",
					"label": "PROXY_DOMAIN",
					"name": "PROXY_DOMAIN"
				}
			],
			"image": "linuxserver/code-server:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/code-server.png",
			"name": "code-server",
			"platform": "linux",
			"ports": [
				"8443:8443/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Code Server",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Code-Server",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Productivity"
			],
			"description": "Codiad is a web-based IDE framework with a small footprint and minimal requirements.\n  ",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/codiad:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/codiad-icon.png",
			"name": "codiad",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Codiad",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Codiad",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Cloud",
				"Books"
			],
			"description": "COPS links to your Calibre library database and allows downloading and emailing of books directly from a web browser and provides a OPDS feed to connect to your devices.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/cops:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/cops-icon.png",
			"name": "cops",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "COPS",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Books",
					"container": "/books"
				},
				{
					"bind": "/portainer/Files/AppData/Config/Cops",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Downloaders",
				"Video"
			],
			"description": "CouchPotato (CP) is an automatic NZB and torrent downloader. You can keep a \"movies I want\"-list and it will search for NZBs/torrents of these movies every X hours. Once a movie is found, it will send it to SABnzbd or download the torrent to a specified directory.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/couchpotato:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/couchpotato-icon.png",
			"name": "couchpotato",
			"platform": "linux",
			"ports": [
				"5050:5050/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "CouchPotato",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Couchpotato",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				},
				{
					"bind": "/portainer/Movies",
					"container": "/movies"
				}
			]
		},
		{
			"categories": [
				"Music"
			],
			"description": "DAAP (iTunes) media server with support for AirPlay devices, Apple Remote (and compatibles), MPD and internet radio.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/daapd:latest",
			"logo": "https://raw.githubusercontent.com/linuxserver/beta-templates/master/lsiodev/img/daapd-icon.png",
			"name": "daapd",
			"platform": "linux",
			"restart_policy": "unless-stopped",
			"title": "Daapd",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Daapd",
					"container": "/config"
				},
				{
					"bind": "/portainer/Music",
					"container": "/music"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "Another application bookmark dashboard, with fun features.",
			"image": "rmountjoy/dashmachine:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/dashmachine_logo.png",
			"name": "dashmachine",
			"platform": "linux",
			"ports": [
				"5000:5000/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "DashMachine",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Dashmachine",
					"container": "/dashmachine/dashmachine/user_data"
				}
			]
		},
		{
			"categories": [
				"FTP",
				"Other",
				"Tools"
			],
			"description": "davos is an FTP automation tool that periodically scans given host locations for new files. It can be configured for various purposes, including listening for specific files to appear in the host location, ready for it to download and then move, if required. It also supports completion notifications as well as downstream API calls, to further the workflow.\r\n\r\n/config : AppData Location\r\n/download : File Download Location",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/davos:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/davos.png",
			"name": "davos",
			"platform": "linux",
			"ports": [
				"8080/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Davos",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Davos",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Music"
			],
			"description": "Deemix is a deezer downloader built from the ashes of Deezloader Remix.",
			"image": "registry.gitlab.com/bockiii/deemix-docker",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/deemix.png",
			"name": "deemix",
			"note": "Deemix may take a few minutes to install. Be sure to check the logs for details. Refer to \u003ca href='https://notabug.org/RemixDevs/DeezloaderRemix/wiki/Login+via+userToken'\u003ethis page\u003c/a\u003e for userToken details.",
			"platform": "linux",
			"ports": [
				"9666:9666/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "DeeMix",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/DeeMix",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				}
			]
		},
		{
			"categories": [
				"Downloaders"
			],
			"description": "Deluge is a lightweight, Free Software, cross-platform BitTorrent client providing: Full Encryption, WebUI, Plugin System, Much more...",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "UMASK",
					"name": "UMASK",
					"set": "000"
				}
			],
			"image": "linuxserver/deluge:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/deluge-icon.png",
			"namme": "deluge",
			"platform": "linux",
			"restart_policy": "unless-stopped",
			"title": "Deluge",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Deluge",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				}
			]
		},
		{
			"categories": [
				"HomeAutomation",
				"Management"
			],
			"description": "Domoticz is a Home Automation System that lets you monitor and configure various devices like: Lights, Switches, various sensors/meters like Temperature, Rain, Wind, UV, Electra, Gas, Water and much more. Notifications/Alerts can be sent to any mobile device",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/domoticz:latest",
			"logo": "https://github.com/domoticz/domoticz/raw/master/www/images/logo.png",
			"name": "domoticz",
			"platform": "linux",
			"ports": [
				"1443:1443/tcp",
				"6144:6144/tcp",
				"8080:8080/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Domoticz",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Domoticz",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"DNS",
				"Tools"
			],
			"description": "Duck DNS is a free service which will point a DNS (sub domains of duckdns.org) to an IP of your choice. The service is completely free, and doesn't require reactivation or forum posts to maintain its existence.\r\n\r\nFirst, go to duckdns site, register your subdomain and retrieve your token\r\nThen run the docker create command above with your subdomain(s) and token\r\nIt will update your IP with the DuckDNS service every 5 minutes\r\n\r\n",
			"env": [
				{
					"label": "SUBDOMAINS",
					"name": "SUBDOMAINS",
					"set": ""
				},
				{
					"label": "TOKEN",
					"name": "TOKEN",
					"set": ""
				},
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/duckdns:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/duckdns.png",
			"name": "duckdns",
			"platform": "linux",
			"restart_policy": "unless-stopped",
			"title": "Duck DNS",
			"type": 1
		},
		{
			"categories": [
				"Backup",
				"Cloud",
				"Other",
				"Productivity",
				"Tools"
			],
			"description": "Free backup software to store encrypted backups online, Duplicati works with standard protocols like FTP, SSH, WebDAV as well as popular services like Microsoft OneDrive, Amazon Cloud Drive and S3, Google Drive, box.com, Mega, hubiC and many others.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/duplicati:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/duplicati-icon.png",
			"name": "duplicati",
			"platform": "linux",
			"ports": [
				"8200:8200/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Duplicati",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Duplicati",
					"container": "/config"
				},
				{
					"container": "/tmp"
				},
				{
					"container": "/backups"
				},
				{
					"container": "/source"
				}
			]
		},
		{
			"categories": [
				"Video",
				"Music",
				"Photos"
			],
			"description": "Emby organizes video, music, live TV, and photos from personal media libraries and streams them to smart TVs, streaming boxes and mobile devices. This container is packaged as a standalone emby Media Server.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "TZ",
					"name": "TZ"
				}
			],
			"image": "linuxserver/emby:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/emby.png",
			"name": "emby",
			"platform": "linux",
			"ports": [
				"8096:8096/tcp",
				"8920:8920/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Emby",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Emby",
					"container": "/config"
				},
				{
					"bind": "/portainer/TV",
					"container": "/data/tvshows"
				},
				{
					"bind": "/portainer/Movies",
					"container": "/data/movies"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "Web File Browser which can be used as a middleware or standalone app.",
			"image": "80x86/filebrowser:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/filebrowser.png",
			"name": "filebrowser",
			"note": "The default user and password is admin/admin.",
			"platform": "linux",
			"ports": [
				"8082:8082/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "FileBrowser",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/FileBrowser",
					"container": "/config"
				},
				{
					"bind": "/portainer/Files/AppData/Config",
					"container": "/myfiles"
				}
			]
		},
		{
			"categories": [
				"Other"
			],
			"description": "A free, self-hostable rss aggregator…",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/freshrss:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/freshrss-icon.png",
			"name": "freshrss",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "FreshRSS",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/freshrss",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Web",
				"Books",
				"Tools"
			],
			"description": "A WebApp Comic Reader for your favorite digital comics. Reach and read your comic library from any web connected device with a modern web browser",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/gazee:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/gazee-logo.png",
			"name": "gazee",
			"platform": "linux",
			"restart_policy": "unless-stopped",
			"title": "Gazee",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Gazee",
					"container": "/config"
				},
				{
					"bind": "/portainer/Comics",
					"container": "/comics"
				},
				{
					"bind": "/portainer/Files/AppData/Gazee",
					"container": "/mylar"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools",
				"Finance"
			],
			"description": "Grocy is an ERP system for your kitchen! Cut down on food waste, and manage your chores with this brilliant utulity.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "Timezone",
					"name": "TZ"
				}
			],
			"image": "linuxserver/grocy:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/grocy_logo.png",
			"name": "grocy",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Grocy",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Grocy",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "A clientless remote desktop gateway.",
			"image": "oznu/guacamole:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/guacamole.png",
			"name": "guacamole",
			"note": "The default login will be guacadmin/guacadmin. It is common practice to add a new admin user and remove the default user for Guacamole.",
			"platform": "linux",
			"ports": [
				"8080:8080/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Guacamole",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Guacamole",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Video",
				"Music",
				"Other"
			],
			"description": "HTPC Manaager, a front end for many htpc related applications. Hellowlol version.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/htpcmanager:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/htpcmanager-icon.png",
			"name": "htpcmanager",
			"platform": "linux",
			"ports": [
				"8085:8085/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "HTPC Manager",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/HTPCmanager",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Downloaders",
				"Music"
			],
			"description": "Lidarr is a music collection manager for Usenet and BitTorrent users.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/lidarr:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/lidarr.png",
			"name": "lidarr",
			"platform": "linux",
			"ports": [
				"8686:8686/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "lidarr",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Lidarr",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				},
				{
					"bind": "/portainer/Music",
					"container": "/music"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "A Linux network-level advertisement and Internet tracker blocking application which acts as a DNS sinkhole.",
			"image": "pihole/pihole:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/pihole.png",
			"name": "pihole",
			"note": "When the installation is complete, navigate to your.ip.goes.here:1010/admin. Follow the article \u003ca href='https://medium.com/@niktrix/getting-rid-of-systemd-resolved-consuming-port-53-605f0234f32f'\u003ehere\u003c/a\u003e if you run into issues binding to port 53.",
			"platform": "linux",
			"ports": [
				"53:53/tcp",
				"53:53/udp",
				"67:67/udp",
				"1010:80/tcp",
				"4443:443/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Pi-Hole",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/PiHole",
					"container": "/etc/pihole"
				},
				{
					"bind": "/portainer/Files/AppData/Config/PiHole/DNS",
					"container": "/etc/dnsmasq.d"
				}
			]
		},
		{
			"categories": [
				"Photos"
			],
			"description": "Piwigo is photo gallery software for the web, built by an active community of users and developers.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/piwigo:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/piwigo-icon.png",
			"name": "piwigo",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Piwigo",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/PiWigo",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Video",
				"Music",
				"Photos"
			],
			"description": "Your favorite movies, TV, music, web shows, podcasts, and more, all streamed to your favorite screens.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "VERSION",
					"name": "VERSION",
					"set": "latest"
				}
			],
			"image": "linuxserver/plex:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/plex-icon.png",
			"name": "plex",
			"network": "host",
			"platform": "linux",
			"restart_policy": "unless-stopped",
			"title": "Plex",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Plex",
					"container": "/config"
				},
				{
					"bind": "/portainer/TV",
					"container": "/tv"
				},
				{
					"bind": "/portainer/Movies",
					"container": "/movies"
				}
			]
		},
		{
			"categories": [
				"Downloaders",
				"Other",
				"Video",
				"Tools"
			],
			"description": "Simple automated way for users to request new content for Plex.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "URL_BASE",
					"name": "URL_BASE",
					"set": ""
				}
			],
			"image": "linuxserver/plexrequests:latest",
			"logo": "https://raw.githubusercontent.com/linuxserver/beta-templates/master/lsiodev/img/plexrequests-icon.png",
			"name": "plexrequests",
			"platform": "linux",
			"ports": [
				"3000:3000/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Plex Requests",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/PlexRequests",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Cloud",
				"Productivity",
				"Tools",
				"Other"
			],
			"description": "ProjectSend is a self-hosted application that lets you upload files and assign them to specific clients that you create yourself! Secure, private and easy. No more depending on external services or e-mail to send those files!\n  ",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/projectsend:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/projectsend-logo.png",
			"name": "projectsend",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "ProjectSend",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/ProjectSend",
					"container": "/data"
				},
				{
					"bind": "/portainer/Files/AppData/Config/ProjectSend",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Email",
				"Productivity",
				"Tools",
				"Other"
			],
			"description": "This is an unofficial Docker container of the ProtonMail Bridge. Some of the scripts are based on Hendrik Meyer's work.",
			"image": "shenxn/protonmail-bridge:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/protonmail-bridge.png",
			"name": "protonmail-bridge",
			"note": "Please refer to the documentation \u003ca href='https://hub.docker.com/r/shenxn/protonmail-bridge'/\u003ehere\u003c/a\u003e to set this up.",
			"platform": "linux",
			"ports": [
				"143/tcp",
				"25/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "ProtonMail Bridge",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/ProtonMail-Bridge",
					"container": "/root"
				}
			]
		},
		{
			"categories": [
				"VPN",
				"Tools",
				"Other",
				"Web"
			],
			"description": "Pritunl container built on Alpine Linux. Supports IPv6 and running behind a reverse proxy. This container requires an external Mongo DB and should be run via Docker Compose or other orchestration.",
			"env": [
				{
					"default": "false",
					"label": "REVERSE_PROXY",
					"name": "REVERSE_PROXY"
				},
				{
					"label": "PRITUNL_OPTS",
					"name": "PRITUNL_OPTS"
				},
				{
					"default": "mongodb://mongo:27017/pritunl",
					"label": "MONGODB_URI",
					"name": "MONGODB_URI"
				},
				{
					"default": "false",
					"label": "WIREGUARD",
					"name": "WIREGUARD"
				}
			],
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/pritunl.png",
			"name": "pritunl",
			"note": "Documentation on this containier can be found here: \u003ca href=https://hub.docker.com/r/goofball222/pritunl\u003ehttps://hub.docker.com/r/goofball222/pritunl\u003c/a\u003e",
			"platform": "linux",
			"repository": {
				"stackfile": "Template/Stack/pritunl.yml",
				"url": "https://github.com/SelfhostedPro/selfhosted_templates"
			},
			"title": "Pritunl",
			"type": 3
		},
		{
			"categories": [
				"Cloud",
				"Other"
			],
			"description": "Pydio (formerly AjaXplorer) is a mature open source software solution for file sharing and synchronization. With intuitive user interfaces (web / mobile / desktop), Pydio provides enterprise-grade features to gain back control and privacy of your data: user directory connectors, legacy filesystems drivers, comprehensive admin interface, and much more.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/pydio:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/pydio-icon.png",
			"name": "pydio",
			"platform": "linux",
			"ports": [
				"443/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Pydio",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Pydio",
					"container": "/config"
				},
				{
					"bind": "/portainer/Files/AppData/Pydio",
					"container": "/data"
				}
			]
		},
		{
			"categories": [
				"Downloaders"
			],
			"description": "The qBittorrent project aims to provide an open-source software alternative to µTorrent. qBittorrent is based on the Qt toolkit and libtorrent-rasterbar library.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/qbittorrent:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/qbittorrent-icon.png",
			"name": "qbittorrent",
			"platform": "linux",
			"ports": [
				"6881:6881/tcp",
				"6881:6881/udp",
				"8080:8080/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "qBittorrent",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/qBittorrent",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				}
			]
		},
		{
			"categories": [
				"Messenger"
			],
			"description": "Quassel IRC is a modern, cross-platform, distributed IRC client, meaning that one (or multiple) client(s) can attach to and detach from a central core -- much like the popular combination of screen and a text-based IRC client such as WeeChat, but graphical. Blowfish support and optional web-ui included.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/quassel-core:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/quassel-core-icon.png",
			"name": "quassel-core",
			"platform": "linux",
			"ports": [
				"4242:4242/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Quassel IRC",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Quassel-core",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Downloaders",
				"Video"
			],
			"description": "Radarr - A fork of Sonarr to work with movies à la Couchpotato.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/radarr:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/radarr.png",
			"name": "radarr",
			"platform": "linux",
			"ports": [
				"7878:7878/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Radarr",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Radarr",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				},
				{
					"bind": "/portainer/Movies",
					"container": "/movies"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "A one-of-a-kind resume builder that's not out to get your data. Completely secure, customizable, portable, open-source and free forever.",
			"image": "amruthpillai/reactive-resume:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/reactiveresume.png",
			"name": "reactive-resume",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Reactive-Resume",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/ReactiveResume",
					"container": "/usr/src/app"
				}
			]
		},
		{
			"categories": [
				"Backup",
				"Cloud",
				"Other",
				"Tools"
			],
			"description": "Resilio Sync (formerly BitTorrent Sync) uses the BitTorrent protocol to sync files and folders between all of your devices. There are both free and paid versions, this container supports both.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/resilio-sync:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/resilio.png",
			"name": "resilio-sync",
			"platform": "linux",
			"restart_policy": "unless-stopped",
			"title": "Resilio Sync",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Resilio-Sync",
					"container": "/config"
				},
				{
					"container": "/sync"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				}
			]
		},
		{
			"categories": [
				"Downloaders"
			],
			"description": "Popular torrent client with a webui for ease of use.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/rutorrent:latest",
			"logo": "https://raw.githubusercontent.com/linuxserver/beta-templates/master/lsiodev/img/rutorrent-icon.png",
			"name": "rutorrent",
			"platform": "linux",
			"ports": [
				"80/tcp",
				"51413:51413/tcp",
				"6881:6881/udp"
			],
			"restart_policy": "unless-stopped",
			"title": "ruTorrent",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/ruTorrent",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				}
			]
		},
		{
			"categories": [
				"Downloaders"
			],
			"description": "SABnzbd makes Usenet as simple and streamlined as possible by automating everything we can. All you have to do is add an .nzb. SABnzbd takes over from there, where it will be automatically downloaded, verified, repaired, extracted and filed away with zero human interaction.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/sabnzbd:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/sabnzbd-icon.png",
			"name": "sabnzbd",
			"platform": "linux",
			"ports": [
				"8080:8080/tcp",
				"9090:9090/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "SABnzbd",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Sabnzbd",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				},
				{
					"bind": "/portainer/Downloads/incomplete",
					"container": "/incomplete-downloads"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "Shiori is a simple bookmarks manager written in Go language. Intended as a simple clone of Pocket. You can use it as command line application or as web application.",
			"image": "radhifadlillah/shiori:latest",
			"logo": "https://raw.githubusercontent.com/robocopAlpha/selfhosted_templates/master/Images/shiori-icon.png",
			"name": "shiori",
			"platform": "linux",
			"ports": [
				"8080/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Shiori",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Shiori",
					"container": "/srv/shiori"
				}
			]
		},
		{
			"categories": [
				"Downloaders",
				"Video"
			],
			"description": "Automatic Video Library Manager for TV Shows. It watches for new episodes of your favorite shows, and when they are posted it does its magic.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/sickchill:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/sickchill-icon.png",
			"name": "sickchill",
			"platform": "linux",
			"ports": [
				"8081:8081/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "SickChill",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/SickChill",
					"container": "/config"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				},
				{
					"bind": "/portainer/TV",
					"container": "/tv"
				}
			]
		},
		{
			"categories": [
				"Downloaders",
				"Video"
			],
			"description": "SickGear provides management of TV shows and/or Anime, it detects new episodes, links downloader apps, and more.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/sickgear:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/sickgear-icon.png",
			"name": "sickgear",
			"platform": "linux",
			"ports": [
				"8081:8081/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "SickGear",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/SickGear",
					"container": "/config"
				},
				{
					"bind": "/portainer/TV",
					"container": "/tv"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				}
			]
		},
		{
			"categories": [
				"Management"
			],
			"description": null,
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/smokeping:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/smokeping-icon.png",
			"name": "smokeping",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "SmokePing",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Smokeping",
					"container": "/config"
				},
				{
					"bind": "/portainer/Files/AppData/Smokeping",
					"container": "/data"
				}
			]
		},
		{
			"categories": [
				"Downloaders",
				"Video"
			],
			"description": "Sonarr (formerly NZBdrone) is a PVR for usenet and bittorrent users. It can monitor multiple RSS feeds for new episodes of your favorite shows and will grab, sort and rename them. It can also be configured to automatically upgrade the quality of files already downloaded when a better quality format becomes available.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/sonarr:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/sonarr-icon.png",
			"name": "sonarr",
			"platform": "linux",
			"ports": [
				"8989:8989/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Sonarr",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Sonarr",
					"container": "/config"
				},
				{
					"bind": "/dev/rtc",
					"container": "/dev/rtc"
				},
				{
					"bind": "/portainer/TV",
					"container": "/tv"
				},
				{
					"bind": "/portainer/Downloads",
					"container": "/downloads"
				}
			]
		},
		{
			"categories": [
				"Backup",
				"Cloud",
				"Other",
				"Tools"
			],
			"description": null,
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/syncthing:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/syncthing-icon.png",
			"name": "syncthing",
			"platform": "linux",
			"ports": [
				"8384:8384/tcp",
				"21027:21027/udp",
				"22000:22000/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "SyncThing",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Syncthing",
					"container": "/config"
				},
				{
					"container": "/sync"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "Tautulli is a 3rd party application that you can run along side your Plex Media Server to monitor activity and track various statistics. Most importantly, these statistics include what has been watched, who watched it, when and where they watched it, and how it was watched. All statistics are presented in a nice and clean interface with many tables and graphs, which makes it easy to brag about your server to everyone else.[br][br]\r\n  [b][u][span style='color: #E80000;']Configuration[/span][/u][/b][br]\r\n  [b]8181[/b] The webui for Tautulli's webui [br]\r\n  [b]/config[/b] Storing Configuration and the Tautulli database[br]\r\n[b]/logs[/b] Map to you plex logs (required for IP logging)[br]\r\n\r\n",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/tautulli:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/tautulli-icon.png",
			"name": "tautulli",
			"platform": "linux",
			"ports": [
				"8181:8181/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Tautulli",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Logs",
					"container": "/logs"
				},
				{
					"bind": "/portainer/Files/AppData/Config/Tautulli",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Messenger"
			],
			"description": "A self-hosted web IRC client",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/thelounge:latest",
			"logo": "https://raw.githubusercontent.com/linuxserver/community-templates/master/lsiocommunity/img/shout-icon.png",
			"name": "thelounge",
			"platform": "linux",
			"ports": [
				"9000:9000/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "TheLounge",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/TheLounge",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "A unique, non-linear notebook wiki.",
			"image": "mazzolino/tiddlywiki:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/tiddlywiki.png",
			"name": "tiddlywiki",
			"platform": "linux",
			"ports": [
				"8080:8080/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "TiddlyWiki",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/TiddlyWiki",
					"container": "/var/lib/tiddlywiki"
				}
			]
		},
		{
			"categories": [
				"Downloaders"
			],
			"description": "Transmission is designed for easy, powerful use. Transmission has the features you want from a BitTorrent client: encryption, a web interface, peer exchange, magnet links, DHT, µTP, UPnP and NAT-PMP port forwarding, webseed support, watch directories, tracker editing, global and per-torrent speed limits, and more.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/transmission:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/transmission-icon.png",
			"name": "transmission",
			"platform": "linux",
			"ports": [
				"9091:9091/tcp",
				"51413:51413/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Transmission",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Transmission",
					"container": "/config"
				},
				{
					"bind": "/portainer/Files/Downloads",
					"container": "/downloads"
				},
				{
					"container": "/watch"
				}
			]
		},
		{
			"categories": [
				"Other",
				"VPN",
				"Tools"
			],
			"description": "This container contains OpenVPN and Transmission with a configuration\nwhere Transmission is running only when OpenVPN has an active tunnel.\nIt bundles configuration files for many popular VPN providers to make the setup easier.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"default": "MULLVAD",
					"description": "https://haugene.github.io/docker-transmission-openvpn/supported-providers/",
					"label": "OPENVPN_PROVIDER",
					"name": "OPENVPN_PROVIDER"
				},
				{
					"default": "",
					"label": "OPENVPN_USERNAME",
					"name": "OPENVPN_USERNAME"
				},
				{
					"default": "",
					"label": "OPENVPN_PASSWORD",
					"name": "OPENVPN_PASSWORD"
				},
				{
					"default": "192.168.0.0/24",
					"label": "LOCAL_NETWORK",
					"name": "LOCAL_NETWORK"
				}
			],
			"image": "haugene/transmission-openvpn:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/transmission-icon.png",
			"name": "transmission-openvpn",
			"note": "List of supported providers available \u003ca href='https://haugene.github.io/docker-transmission-openvpn/supported-providers'/\u003ehere\u003c/a\u003e.",
			"platform": "linux",
			"ports": [
				"9091:9091/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Transmission-OpenVPN",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Downloads",
					"container": "/data"
				},
				{
					"bind": "/etc/localtime",
					"container": "/etc/localtime"
				}
			]
		},
		{
			"categories": [
				"Other"
			],
			"description": "Tiny Tiny RSS is an open source web-based news feed (RSS/Atom) reader and aggregator, designed to allow you to read news from any location, while feeling as close to a real desktop application as possible.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "lunik1/tt-rss:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/tt-rss-icon.png",
			"name": "tt-rss",
			"platform": "linux",
			"ports": [
				"80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Tiny Tiny RSS",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/tt-rss",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Video",
				"Other"
			],
			"description": "Tvheadend is a TV streaming server and recorder for Linux, FreeBSD and Android supporting DVB-S, DVB-S2, DVB-C, DVB-T, ATSC, ISDB-T, IPTV, SAT\u0026gt;IP and HDHomeRun as input sources.\r\nTvheadend offers the HTTP (VLC, MPlayer), HTSP (Kodi, Movian) and SAT\u0026gt;IP streaming.\r\nMultiple EPG sources are supported (over-the-air DVB and ATSC including OpenTV DVB extensions, XMLTV, PyXML).",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/tvheadend:latest",
			"logo": "http://i.imgur.com/zGSUAT4.png",
			"name": "tvheadend",
			"platform": "linux",
			"ports": [
				"9981:9981/tcp",
				"9982:9982/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Tvheadend",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/TVHeadend",
					"container": "/config"
				},
				{
					"container": "/recordings"
				}
			]
		},
		{
			"categories": [
				"Cloud",
				"Books"
			],
			"description": "Ubooquity is a free, lightweight and easy-to-use home server for your comics and ebooks. Use it to access your files from anywhere, with a tablet, an e-reader, a phone or a computer.",
			"env": [
				{
					"label": "MAXMEM",
					"name": "MAXMEM",
					"set": "512"
				},
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/ubooquity:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/ubooquity-icon.png",
			"name": "ubooquity",
			"platform": "linux",
			"ports": [
				"2202:2202/tcp",
				"2203:2203/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Ubooquity",
			"type": 1,
			"volumes": [
				{
					"container": "/books"
				},
				{
					"container": "/comics"
				},
				{
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Management",
				"Tools"
			],
			"description": null,
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/unifi-controller:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/unifi-icon.png",
			"name": "unifi-controller",
			"platform": "linux",
			"ports": [
				"3478:3478/udp",
				"10001:10001/udp",
				"8080:8080/tcp",
				"8081:8081/tcp",
				"8443:8443/tcp",
				"8843:8843/tcp",
				"8880:8880/tcp",
				"6789:6789/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "UniFi Controller",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Unifi",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools",
				"Maintenance"
			],
			"description": "With watchtower you can update the running version of your containerized app simply by pushing a new image to the Docker Hub or your own image registry. Watchtower will pull down your new image, gracefully shut down your existing container and restart it with the same options that were used when it was deployed initially.",
			"image": "containrrr/watchtower:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/watchtower.png",
			"name": "watchtower",
			"note": "It is recommended to manually update your containers but we're including this for those of you that don't care",
			"platform": "linux",
			"restart_policy": "unless-stopped",
			"title": "Watchtower",
			"type": 1,
			"volumes": [
				{
					"bind": "/var/run/docker.sock",
					"container": "/var/run/docker.sock"
				}
			]
		},
		{
			"categories": [
				"Downloaders"
			],
			"description": "WebGrab+Plus is a multi-site incremental xmltv epg grabber. It collects tv-program guide data from selected tvguide sites for your favourite channels.[br]\r\n\t\tOptional postprocessors to add IMDb data or to customize your xmltv listing.[br]\r\n\t\thttp://www.webgrabplus.com/[br]\r\n\t\t[b][span style='color: #E80000;']Directions:[/span][/b][br]\r\n\t\t[b]/config[/b] : This is where WebGrab+Plus will store it's configuration.[br][br]\r\n\t\t[b]/data[/b] : This is where tv_grab_wg script in the Tvheadend container looks for the guide.xml file.[br][br]",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/webgrabplus:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/webgrabplus.png",
			"name": "webgrabplus",
			"platform": "linux",
			"restart_policy": "unless-stopped",
			"title": "WebGrab+Plus",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/WebGrabPlus",
					"container": "/config"
				},
				{
					"bind": "/portainer/Files/AppData/WebGrabPlus",
					"container": "/data"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "Self-hosted, ad-free, privacy-respecting Google metasearch engine.",
			"image": "benbusby/whoogle-search:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/whoogle.png",
			"name": "whoogle",
			"platform": "linux",
			"ports": [
				"5001:5000/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Whoogle",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Whoogle",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "Wikijs A modern, lightweight and powerful wiki app built on NodeJS.",
			"image": "linuxserver/wikijs:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/wikijs.png",
			"name": "wikijs",
			"platform": "linux",
			"ports": [
				"3100:3000/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Wikijs",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/Wikijs",
					"container": "/config"
				},
				{
					"bind": "/portainer/Files/AppData/Config/Wikijs/data",
					"container": "/data"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Downloaders"
			],
			"description": "YoutubeDL-Material is a Material Design frontend for youtube-dl. It's coded using Angular 9 for the frontend, and Node.js on the backend.",
			"image": "tzahi12345/youtubedl-material:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/ytdlm.png",
			"name": "youtubedl-material",
			"platform": "linux",
			"ports": [
				"17442:17442/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "YouTubeDL-Material",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/YTDLM",
					"container": "/app/appdata"
				},
				{
					"bind": "/portainer/Files/AppData/Youtube/Video",
					"container": "/app/video"
				},
				{
					"bind": "/portainer/Files/AppData/Youtube/Subscriptions",
					"container": "/app/subscriptions"
				},
				{
					"bind": "/portainer/Files/AppData/Youtube/Users",
					"container": "/app/users"
				},
				{
					"bind": "/portainer/Files/AppData/Youtube/Audio",
					"container": "/app/audio"
				}
			]
		},
		{
			"categories": [
				"CCTV"
			],
			"description": "UniFi Video is a powerful and flexible, integrated IP video management surveillance system designed to work with Ubiquiti’s UniFi Video Camera product line. UniFi Video has an intuitive, configurable, and feature‑packed user interface with advanced features such as motion detection, auto‑discovery, user‑level security, storage management, reporting, and mobile device support.",
			"env": [
				{
					"default": "99",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"default": "002",
					"label": "UMASK",
					"name": "UMASK"
				},
				{
					"label": "CONTEXT_PATH",
					"name": "CONTEXT_PATH",
					"set": "UniFi Video"
				}
			],
			"image": "pducharme/unifi-video-controller:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/UniFiVideo-logo.png",
			"name": "UniFi Video",
			"platform": "linux",
			"ports": [
				"1935:1935/tcp",
				"7444:7444/tcp",
				"7447:7447/tcp",
				"6666:6666/tcp",
				"7442:7442/tcp",
				"7080:7080/tcp",
				"7443:7443/tcp",
				"7445:7445/tcp",
				"7446:7446/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "UniFi Video",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/UnifFiVideo/Recordings/",
					"container": "/recordings"
				},
				{
					"bind": "/portainer/Files/AppData/Config/UniFiVideo/",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "A web interface for managing docker containers with an emphasis on templating to provide 1 click deployments. Think of it like a decentralized app store for servers that anyone can make packages for.",
			"image": "selfhostedpro/yacht:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/Yacht/master/readme_media/Yacht_logo_1_dark.png",
			"name": "yacht",
			"platform": "linux",
			"ports": [
				"8001:8000/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Yacht",
			"type": 1,
			"volumes": [
				{
					"bind": "yacht",
					"container": "/config"
				},
				{
					"bind": "/var/run/docker.sock",
					"container": "/var/run/docker.sock"
				}
			]
		},
		{
			"categories": [
				"Messenger"
			],
			"description": "ZNC is an IRC network bouncer or BNC. It can detach the client from the actual IRC server, and also from selected channels. Multiple clients from different locations can connect to a single ZNC account simultaneously and therefore appear under the same nickname on IRC.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "linuxserver/znc:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/znc-icon.png",
			"name": "znc",
			"platform": "linux",
			"ports": [
				"6501:6501/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "ZNC",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/ZNC",
					"container": "/config"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Tools"
			],
			"description": "NOTE: Once you deploy your GoPhish instance, please navigate to the logs section in Portainer and acquire your 'admin' credentials for login. Gophish is an open-source phishing toolkit designed for businesses and penetration testers. It provides the ability to quickly and easily setup and execute phishing engagements and security awareness training.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "100",
					"label": "PGID",
					"name": "PGID"
				}
			],
			"image": "gophish/gophish:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/gophish.png",
			"name": "gophish",
			"platform": "linux",
			"ports": [
				"3333:3333/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "GOPHISH",
			"type": 1
		},
		{
			"categories": [
				"Cloud",
				"Other"
			],
			"description": "Seafile is an open-source, cross-platform file-hosting software system. Files are stored on a central server and can be synchronized with personal computers and mobile devices through apps. Files on the Seafile server can also be accessed directly via the server's web interface.",
			"env": [
				{
					"default": "Etc/UTC",
					"label": "Time Zone",
					"name": "TIME_ZONE"
				},
				{
					"default": "password",
					"label": "Database Password",
					"name": "MYSQL_ROOT_PASSWORD"
				},
				{
					"default": "me@example.com",
					"label": "Administrator Email",
					"name": "ADMIN_EMAIL"
				},
				{
					"default": "asecret",
					"label": "Administrator Password",
					"name": "ADMIN_PASSWORD"
				},
				{
					"default": "docs.seafile.com",
					"label": "Domain Name",
					"name": "SERVER_HOSTNAME"
				},
				{
					"label": "Enable HTTPS?",
					"name": "ENABLE_HTTPS",
					"select": [
						{
							"default": true,
							"text": "Yes",
							"value": "true"
						},
						{
							"text": "No",
							"value": "false"
						}
					]
				}
			],
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/seafile.png",
			"name": "seafile",
			"platform": "linux",
			"repository": {
				"stackfile": "Template/Stack/seafile.yml",
				"url": "https://github.com/SelfhostedPro/selfhosted_templates"
			},
			"title": "Seafile",
			"type": 3
		},
		{
			"categories": [
				"Other",
				"Tools",
				"Maintenance"
			],
			"description": "Dozzle is a simple, lightweight application that provides you with a web based interface to monitor your Docker container logs live. It doesn’t store log information, it is for live monitoring of your container logs only.",
			"image": "amir20/dozzle:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/dozzle.png",
			"name": "dozzle",
			"platform": "linux",
			"ports": [
				"8080:8080/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Dozzle",
			"type": 1,
			"volumes": [
				{
					"bind": "/var/run/docker.sock",
					"container": "/var/run/docker.sock"
				}
			]
		},
		{
			"categories": [
				"Tools",
				"Productivity",
				"Web",
				"Other"
			],
			"description": "wallabag is a self hostable application for saving web pages: Save and classify articles. Read them later. Freely.",
			"env": [
				{
					"default": "ovmpmAWXRCabNlMgzlzFXDYmCFfzGv",
					"description": "This should be set to a random string of characters.",
					"label": "Secret",
					"name": "SYMFONY__ENV__SECRET"
				},
				{
					"default": "https://wallabag.example.com",
					"label": "Domain Name",
					"name": "SYMFONY__ENV__DOMAIN_NAME"
				},
				{
					"default": "127.0.0.1",
					"label": "SMTP Host",
					"name": "SYMFONY__ENV__MAILER_HOST"
				},
				{
					"default": "~",
					"label": "SMTP Username",
					"name": "SYMFONY__ENV__MAILER_USER"
				},
				{
					"default": "~",
					"label": "SMTP Password",
					"name": "SYMFONY__ENV__MAILER_PASSWORD"
				},
				{
					"default": "wallabag@example.com",
					"label": "SMTP From Email",
					"name": "SYMFONY__ENV__FROM_EMAIL"
				},
				{
					"label": "Enable public user registration?",
					"name": "SYMFONY__ENV__FOSUSER_REGISTRATION",
					"select": [
						{
							"default": true,
							"text": "Yes",
							"value": "true"
						},
						{
							"text": "No",
							"value": "false"
						}
					]
				},
				{
					"label": "Require registration confirmation?",
					"name": "SYMFONY__ENV__FOSUSER_CONFIRMATION",
					"select": [
						{
							"default": true,
							"text": "Yes",
							"value": "true"
						},
						{
							"text": "No",
							"value": "false"
						}
					]
				}
			],
			"image": "wallabag/wallabag:latest",
			"logo": "https://raw.githubusercontent.com/jake-walker/selfhosted_templates/wallabag/Images/wallabag.png",
			"name": "wallabag",
			"platform": "linux",
			"ports": [
				"80:80/tcp"
			],
			"restart_policy": "unless-stopped",
			"title": "Wallbag",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Wallabag/data",
					"container": "/var/www/wallabag/data"
				},
				{
					"bind": "/portainer/Files/AppData/Wallabag/images",
					"container": "/var/www/wallabag/web/assets/images"
				}
			]
		},
		{
			"categories": [
				"Other",
				"Utilities"
			],
			"description": "DDClient is a Perl client used to update dynamic DNS entries for accounts on Dynamic DNS Network Service Provider. It was originally written by Paul Burry and is now mostly by wimpunk. It has the capability to update more than just dyndns and it can fetch your WAN-ipaddress in a few different ways.",
			"env": [
				{
					"default": "1000",
					"label": "PUID",
					"name": "PUID"
				},
				{
					"default": "1000",
					"label": "PGID",
					"name": "PGID"
				},
				{
					"label": "CONTEXT_PATH",
					"name": "CONTEXT_PATH",
					"set": "ddclient"
				},
				{
					"label": "JAVA_OPTS",
					"name": "JAVA_OPTS",
					"set": "-Xms256m -Xmx512m"
				},
				{
					"label": "TZ",
					"name": "TZ"
				}
			],
			"image": "linuxserver/ddclient:latest",
			"logo": "https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/master/Images/ddclient.png",
			"name": "ddclient",
			"platform": "linux",
			"restart_policy": "unless-stopped",
			"title": "DDClient",
			"type": 1,
			"volumes": [
				{
					"bind": "/portainer/Files/AppData/Config/DDClient/",
					"container": "/config"
				}
			]
		}
	]
}
