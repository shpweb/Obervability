Reference: [https://grafana.com/tutorials/grafana-fundamentals/](url)

<!doctype html>
<html lang=en>

<body class=section-tutorials>
    <div class=main>
        <div class=main-content>
            <div class=tutorial-header>
                <h1 class="wrapper text-white">Grafana fundamentals</h1>
            </div>
            <div class=wrapper>
                <div x-data=scrollspy() x-init=spy() @scroll.window.debounce.100=spy()>
                    <div class="row m-0">
                        <div class="col--xs-12 col--md-3">
                            <aside class=tutorial-sidebar>
                                <h4>On this page</h4>
                                <ol class="tutorial-toc scrollspy-links">
                                    <li>
                                        <a href=#introduction>
                                            <span>Introduction</span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href=#set-up-the-sample-application>
                                            <span>Set up the sample application</span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href=#log-in-to-grafana>
                                            <span>Log in to Grafana</span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href=#add-a-metrics-data-source>
                                            <span>Add a metrics data source</span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href=#explore-your-metrics>
                                            <span>Explore your metrics</span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href=#add-a-logging-data-source>
                                            <span>Add a logging data source</span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href=#explore-your-logs>
                                            <span>Explore your logs</span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href=#build-a-dashboard>
                                            <span>Build a dashboard</span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href=#annotate-events>
                                            <span>Annotate events</span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href=#create-a-grafana-managed-alert>
                                            <span>Create a Grafana Managed Alert</span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href=#summary>
                                            <span>Summary</span>
                                        </a>
                                    </li>
                                </ol>
                                <ul class=tutorial-toc>
                                    <li><svg width="14" height="14" viewBox="0 0 14 14" fill="none"
                                            xmlns="http://www.w3.org/2000/svg">
                                            <path
                                                d="M6.90545 10.0747c.19686.0.39372.199999999999999.39372.4001.0.199999999999999-.19686.4-.39372.4-.19687.0-.39373-.200000000000001-.39373-.4.0-.200100000000001.19686-.4001.39373-.4001z"
                                                fill="#ff8d0b" stroke="#fa650f" stroke-width="1.5"
                                                stroke-linecap="round" stroke-linejoin="round" />
                                            <path d="M6.90527 7.87435V4.87402" stroke="#ff8d0b" stroke-width="1.5"
                                                stroke-linecap="round" stroke-linejoin="round" />
                                            <path
                                                d="M12.615 10.4749C13.0087 11.375 12.7134 12.3751 11.8275 12.8751 11.6306 12.9752 11.3353 13.0752 11.04 13.0752H2.77177C1.78745 13.0752 1 12.2751 1 11.275 1 10.9749 1.09843 10.7749 1.19686 10.4749L5.331 1.97394c.39373-.9001 1.47648-1.200129 2.36237-.80009C7.98866 1.37388 8.28396 1.67391 8.48082 1.97394L12.615 10.4749z"
                                                stroke="#ff8d0b" stroke-width="1.5" stroke-linecap="round"
                                                stroke-linejoin="round" />
                                        </svg>
                                        <a class=ml-1 href=https://github.com/grafana/tutorials/issues/new>Report a
                                            mistake</a>
                                    </li>
                                    <li><svg width="13" height="15" viewBox="0 0 13 15" fill="none"
                                            xmlns="http://www.w3.org/2000/svg">
                                            <path
                                                d="M11.7813 12.7871C11.7813 13.0026 11.6956 13.2093 11.5433 13.3616 11.3909 13.514 11.1842 13.5996 10.9688 13.5996H2.03125C1.81576 13.5996 1.6091 13.514 1.45673 13.3616 1.30435 13.2093 1.21875 13.0026 1.21875 12.7871V2.22461c0-.21549.0855999999999999-.42215.23798-.57452.15237-.15238.35903-.23798.57452-.23798H7.78863C8.00396 1.41216 8.21048 1.49768 8.36279 1.6499L11.5435 4.83057c.152200000000001.15231.2377.35883.2378.57416V12.7871z"
                                                stroke="#ff8d0b" stroke-width="1.5" stroke-linecap="round"
                                                stroke-linejoin="round" />
                                            <path
                                                d="M11.7813 5.47461H8.53125C8.31576 5.47461 8.1091 5.38901 7.95673 5.23663c-.15238-.15237-.23798-.35903-.23798-.57452v-3.25"
                                                stroke="#ff8d0b" stroke-width="1.5" stroke-linecap="round"
                                                stroke-linejoin="round" />
                                            <path d="M3.79199 8.04175H9.20866" stroke="#ff8d0b" stroke-width="1.5"
                                                stroke-linecap="round" stroke-linejoin="round" />
                                            <path d="M3.79199 11H9.20866" stroke="#ff8d0b" stroke-width="1.5"
                                                stroke-linecap="round" stroke-linejoin="round" />
                                        </svg>
                                        <a class=ml-1 href=/docs>View documentation</a>
                                    </li>
                                    <li><svg width="15" height="15" viewBox="0 0 15 15" fill="none"
                                            xmlns="http://www.w3.org/2000/svg">
                                            <g clip-path="url(#clip0)">
                                                <path
                                                    d="M7.5625 11.9375C7.33044 11.9375 7.10788 11.8453 6.94378 11.6812 6.77969 11.5171 6.6875 11.2946 6.6875 11.0625V6.6875c0-.23206.0921900000000004-.45462.25628-.61872C7.10788 5.90469 7.33044 5.8125 7.5625 5.8125h6.125C13.9196 5.8125 14.1421 5.90469 14.3062 6.06878 14.4703 6.23288 14.5625 6.45544 14.5625 6.6875v4.375C14.5625 11.2946 14.4703 11.5171 14.3062 11.6812 14.1421 11.8453 13.9196 11.9375 13.6875 11.9375h-.875v2.625l-2.625-2.625H7.5625z"
                                                    stroke="#ff8d0b" stroke-width="1.5" stroke-linecap="round"
                                                    stroke-linejoin="round" />
                                                <path
                                                    d="M4.9375 8.4375l-1.75 1.75V7.5625h-.875C2.08044 7.5625 1.85788 7.47031 1.69378 7.30622 1.52969 7.14212 1.4375 6.91956 1.4375 6.6875V2.3125c0-.23206.09219-.45462.25628-.61872.1641-.16409.38666-.25628.61872-.25628h6.125c.232060000000001.0.45462.09219.61872.25628.16409.1641.25628.38666.25628.61872v1.75"
                                                    stroke="#ff8d0b" stroke-width="1.5" stroke-linecap="round"
                                                    stroke-linejoin="round" />
                                            </g>
                                            <defs>
                                                <clipPath id="clip0">
                                                    <rect width="15" height="15" fill="#fff" />
                                                </clipPath>
                                            </defs>
                                        </svg>
                                        <a class=ml-1 href=https://community.grafana.com />Community Forums</a>
                                    </li>
                                </ul>
                                <br>
                                <div x-data='app_form({"action":"/newsletter/subscribe","body":false,"campaign_id":false,"content_bottom":" ","fields":[{"element":"input","label":"Email","name":"email","type":"email"}],"name":"docs-newsletter","subject":false,"submit":"Subscribe","success":"Thanks for signing up!"}, &#39;&#39;)'
                                    x-init=init() class=alpine-form x-cloak>
                                    <h5>Newsletter</h5>
                                    <p>Want to stay on top of Grafana and Observability news? Sign up for our
                                        newsletter.</p>
                                    <form @submit.prevent=submit()>
                                        <template x-if=!response>
                                            <div>
                                                <template x-for="field in form.fields" :key=field>
                                                    <div class=alpine-form__wrap>
                                                        <template
                                                            x-if="field.element === 'input' && field.type === 'email'">
                                                            <div :class="field.wrapperClass || 'form-input'">
                                                                <label x-text="field.label + '*'"
                                                                    x-show="field.hideLabel === true ? false : true"></label>
                                                                <template x-if="email !== ''">
                                                                    <input :name=field.name :value=email
                                                                        :placeholder="field.placeholder || field.label"
                                                                        :type=field.type
                                                                        @input="set_value($event, field.name)"
                                                                        :class=field.inputClass :aria-label=field.label
                                                                        :required="field.required === false ? undefined : true">
                                                                </template>
                                                                <template x-if="email === ''">
                                                                    <input :name=field.name
                                                                        :placeholder="field.placeholder || field.label"
                                                                        :type=field.type
                                                                        @input="set_value($event, field.name)"
                                                                        :class=field.inputClass :aria-label=field.label
                                                                        :required="field.required === false ? undefined : true">
                                                                </template>
                                                            </div>
                                                        </template>
                                                        <template
                                                            x-if="field.element === 'input' && field.type !== 'email'">
                                                            <div :class="field.wrapperClass || 'form-input'">
                                                                <label x-text="field.label + '*'"
                                                                    x-show="field.hideLabel === true ? false : true"></label>
                                                                <input :name=field.name
                                                                    :placeholder="field.placeholder || field.label"
                                                                    :type=field.type
                                                                    @input="set_value($event, field.name)"
                                                                    :class=field.inputClass :aria-label=field.label
                                                                    :required="field.required === false ? undefined : true">
                                                            </div>
                                                        </template>
                                                        <div class=form-submit>
                                                            <template x-if=form.submit_btn>
                                                                <button class="btn btn--primary w-100 br-4"
                                                                    :class=form.submit_btn type=submit
                                                                    x-text=form.submit></button>
                                                            </template>
                                                            <template x-if=!form.submit_btn>
                                                                <button class="btn btn--primary w-100 br-4" type=submit
                                                                    x-text=form.submit></button>
                                                            </template>
                                                        </div>
                                                    </div>
                                                </template>
                                            </div>
                                        </template>
                                        <template x-if="response === true && form.success">
                                            <div>
                                                <h5 class="form-response form-response__success inter m-0"
                                                    x-text=form.success></h5>
                                            </div>
                                        </template>
                                        <template x-if="response === true && !form.success">
                                            <div>
                                                <h5 class="form-response form-response__success inter m-0">Success!</h5>
                                            </div>
                                        </template>
                                        <template class="form-response form-response--error mt-1"
                                            x-if="response === false">
                                            <p class="form-response form-response--success text-white mt-1">
                                                Sorry, an error occurred. Email <a class="text-white text-underline"
                                                    href=mailto:update@grafana.com>update@grafana.com</a> for help.
                                            </p>
                                        </template>
                                    </form>
                                </div>
                            </aside>
                        </div>
                        <main class="col--xs-12 col--md-9">
                            <div class=tutorial-content>
                                <div class=tutorial-content__wrap>
                                    <div class=tutorial-authors>
                                        <div class="row mb-1 author-container d-flex align-items-center">
                                            <div class=mr-1>
                                                <img class="lazyload br-50"
                                                    data-src=/static/img/about/grafana_logo_swirl_fullcolor.jpg
                                                    src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw=="
                                                    alt="Grafana Labs Team" width=41>
                                            </div>
                                            <div class="d-flex align-items-center">
                                                <div>
                                                    <h5 class="p-0 mb-0"> By
                                                        Grafana Labs Team
                                                    </h5>
                                                    <p class="p-0 mb-0">Last update on June 7, 2022</p>
                                                </div>
                                            </div>
                                        </div>
                                        <div class=pb-1>
                                            <span class=tutorial-tag>Beginner</span>
                                        </div>
                                    </div>
                                    <p>
                                    <div id=introduction class=scrollspy-content>
                                        <h2 id=introduction>Introduction</h2>
                                        <p>In this tutorial, you&rsquo;ll learn how to use Grafana to set up a
                                            monitoring solution for your application.</p>
                                        <p>In this tutorial, you&rsquo;ll:</p>
                                        <ul>
                                            <li>Explore metrics and logs</li>
                                            <li>Build dashboards</li>
                                            <li>Annotate dashboards</li>
                                            <li>Set up alerts</li>
                                        </ul>
                                        <div class=prerequisite-section>
                                            <h3 id=prerequisites>Prerequisites</h3>
                                            <ul>
                                                <li><a href=https://docs.docker.com/install/ target=_blank
                                                        rel="noopener noreferrer">Docker</a></li>
                                                <li><a href=https://docs.docker.com/compose/ target=_blank
                                                        rel="noopener noreferrer">Docker Compose</a> (included in Docker
                                                    for Desktop for macOS and Windows)</li>
                                                <li><a href=https://git-scm.com/ target=_blank
                                                        rel="noopener noreferrer">Git</a></li>
                                            </ul>
                                        </div>
                                    </div>
                                    <div id=set-up-the-sample-application class=scrollspy-content>
                                        <h2 id=set-up-the-sample-application>Set up the sample application</h2>
                                        <p>This tutorial uses a sample application to demonstrate some of the features
                                            in Grafana. To complete the exercises in this tutorial, you need to download
                                            the files to your local machine.</p>
                                        <p>In this step, you&rsquo;ll set up the sample application, as well as
                                            supporting services, such as <a href=https://prometheus.io />Prometheus</a>
                                            and <a href=https://grafana.com/oss/loki />Loki</a>.</p>
                                        <ol>
                                            <li>
                                                <p>Clone the <a
                                                        href=https://github.com/grafana/tutorial-environment>github.com/grafana/tutorial-environment</a>
                                                    repository.</p>
                                                <pre><code>git clone https://github.com/grafana/tutorial-environment.git
</code></pre>
                                            </li>
                                            <li>
                                                <p>Change to the directory where you cloned this repository:</p>
                                                <pre><code>cd tutorial-environment
</code></pre>
                                            </li>
                                            <li>
                                                <p>Make sure Docker is running:</p>
                                                <pre><code>docker ps
</code></pre>
                                                <p>No errors means it is running. If you get an error, then start Docker
                                                    and then run the command again.</p>
                                            </li>
                                            <li>
                                                <p>Start the sample application:</p>
                                                <pre><code>docker-compose up -d
</code></pre>
                                                <p>The first time you run <code>docker-compose up -d</code>, Docker
                                                    downloads all the necessary resources for the tutorial. This might
                                                    take a few minutes, depending on your internet connection.</p>
                                                <blockquote>
                                                    <p><strong>Note:</strong> If you already have Grafana, Loki, or
                                                        Prometheus running on your system, then you might see errors
                                                        because the Docker image is trying to use ports that your local
                                                        installations are already using. Stop the services, then run the
                                                        command again.</p>
                                                </blockquote>
                                            </li>
                                            <li>
                                                <p>Ensure all services are up-and-running:</p>
                                                <pre><code>docker-compose ps
</code></pre>
                                                <p>In the <strong>State</strong> column, it should say <code>Up</code>
                                                    for all services.</p>
                                            </li>
                                            <li>
                                                <p>Browse to the sample application on <a
                                                        href=http://localhost:8081>localhost:8081</a>.</p>
                                            </li>
                                        </ol>
                                        <h3 id=grafana-news>Grafana News</h3>
                                        <p>The sample application, Grafana News, lets you post links and vote for the
                                            ones you like.</p>
                                        <p>To add a link:</p>
                                        <ol>
                                            <li>
                                                <p>In <strong>Title</strong>, enter <strong>Example</strong>.</p>
                                            </li>
                                            <li>
                                                <p>In <strong>URL</strong>, enter <strong><a
                                                            href=https://example.com>https://example.com</a></strong>.
                                                </p>
                                            </li>
                                            <li>
                                                <p>Click <strong>Submit</strong> to add the link.</p>
                                                <p>The link appears in the list under the Grafana News heading.</p>
                                            </li>
                                        </ol>
                                        <p>To vote for a link, click the triangle icon next to the name of the link.</p>
                                    </div>
                                    <div id=log-in-to-grafana class=scrollspy-content>
                                        <h2 id=log-in-to-grafana>Log in to Grafana</h2>
                                        <p>Grafana is an open-source platform for monitoring and observability that lets
                                            you visualize and explore the state of your systems.</p>
                                        <ol>
                                            <li>
                                                <p>Open a new tab.</p>
                                            </li>
                                            <li>
                                                <p>Browse to <a href=http://localhost:3000>localhost:3000</a>.</p>
                                            </li>
                                            <li>
                                                <p>In <strong>email or username</strong>, enter <strong>admin</strong>.
                                                </p>
                                            </li>
                                            <li>
                                                <p>In <strong>password</strong>, enter <strong>admin</strong>.</p>
                                            </li>
                                            <li>
                                                <p>Click <strong>Log In</strong>.</p>
                                                <p>The first time you log in, you&rsquo;re asked to change your
                                                    password:</p>
                                            </li>
                                            <li>
                                                <p>In <strong>New password</strong>, enter your new password.</p>
                                            </li>
                                            <li>
                                                <p>In <strong>Confirm new password</strong>, enter the same password.
                                                </p>
                                            </li>
                                            <li>
                                                <p>Click <strong>Save</strong>.</p>
                                            </li>
                                        </ol>
                                        <p>The first thing you see is the Home dashboard, which helps you get started.
                                        </p>
                                        <p>To the far left you can see the <em>sidebar</em>, a set of quick access icons
                                            for navigating Grafana.</p>
                                    </div>
                                    <div id=add-a-metrics-data-source class=scrollspy-content>
                                        <h2 id=add-a-metrics-data-source>Add a metrics data source</h2>
                                        <p>The sample application exposes metrics which are stored in <a
                                                href=https://prometheus.io />Prometheus</a>, a popular time series
                                            database (TSDB).</p>
                                        <p>To be able to visualize the metrics from Prometheus, you first need to add it
                                            as a data source in Grafana.</p>
                                        <ol>
                                            <li>
                                                <p>In the side bar, hover your cursor over the
                                                    <strong>Configuration</strong> (gear) icon, and then click
                                                    <strong>Data Sources</strong>.</p>
                                            </li>
                                            <li>
                                                <p>Click <strong>Add data source</strong>.</p>
                                            </li>
                                            <li>
                                                <p>In the list of data sources, click <strong>Prometheus</strong>.</p>
                                            </li>
                                            <li>
                                                <p>In the URL box, enter <strong>http://prometheus:9090</strong>.</p>
                                            </li>
                                            <li>
                                                <p>Click <strong>Save & Test</strong>.</p>
                                                <p>Prometheus is now available as a data source in Grafana.</p>
                                            </li>
                                        </ol>
                                    </div>
                                    <div id=explore-your-metrics class=scrollspy-content>
                                        <h2 id=explore-your-metrics>Explore your metrics</h2>
                                        <p>Grafana Explore is a workflow for troubleshooting and data exploration. In
                                            this step, you&rsquo;ll be using Explore to create ad-hoc queries to
                                            understand the metrics exposed by the sample application.</p>
                                        <blockquote>
                                            <p>Ad-hoc queries are queries that are made interactively, with the purpose
                                                of exploring data. An ad-hoc query is commonly followed by another, more
                                                specific query.</p>
                                        </blockquote>
                                        <ol>
                                            <li>
                                                <p>In the side bar, click the <strong>Explore</strong> (compass rose)
                                                    icon.</p>
                                            </li>
                                            <li>
                                                <p>In the <strong>Query editor</strong>, where it says <em>Enter a
                                                        PromQL query</em>, enter
                                                    <code>tns_request_duration_seconds_count</code> and then press Shift
                                                    + Enter.
                                                    A graph appears.</p>
                                            </li>
                                            <li>
                                                <p>In the top right corner, click the dropdown arrow on the <strong>Run
                                                        Query</strong> button, and then select <strong>5s</strong>.
                                                    Grafana runs your query and updates the graph every 5 seconds.</p>
                                                <p>You just made your first <em>PromQL</em> query! <a
                                                        href=https://prometheus.io/docs/prometheus/latest/querying/basics />PromQL</a>
                                                    is a powerful query language that lets you select and aggregate time
                                                    series data stored in Prometheus.</p>
                                                <p><code>tns_request_duration_seconds_count</code> is a
                                                    <em>counter</em>, a type of metric whose value only ever increases.
                                                    Rather than visualizing the actual value, you can use counters to
                                                    calculate the <em>rate of change</em>, i.e. how fast the value
                                                    increases.</p>
                                            </li>
                                            <li>
                                                <p>Add the <code>rate</code> function to your query to visualize the
                                                    rate of requests per second. Enter the following in the
                                                    <strong>Query editor</strong> and then press Shift + Enter.</p>
                                                <pre><code>rate(tns_request_duration_seconds_count[5m])
</code></pre>
                                                <p>Immediately below the graph there&rsquo;s an area where each time
                                                    series is listed with a colored icon next to it. This area is called
                                                    the <em>legend</em>.</p>
                                                <p>PromQL lets you group the time series by their labels, using the
                                                    <code>sum</code> function.</p>
                                            </li>
                                            <li>
                                                <p>Add the <code>sum</code> function to your query to group time series
                                                    by route:</p>
                                                <pre><code>sum(rate(tns_request_duration_seconds_count[5m])) by(route)
</code></pre>
                                            </li>
                                            <li>
                                                <p>Go back to the <a href=http://localhost:8081>sample application</a>
                                                    and generate some traffic by adding new links, voting, or just
                                                    refresh the browser.</p>
                                            </li>
                                            <li>
                                                <p>In the upper right corner, click the <em>time picker</em>, and select
                                                    <strong>Last 5 minutes</strong>. By zooming in on the last few
                                                    minutes, it&rsquo;s easier to see when you receive new data.</p>
                                            </li>
                                        </ol>
                                        <p>Depending on your use case, you might want to group on other labels. Try
                                            grouping by other labels, such as <code>status_code</code>, by changing the
                                            <code>by(route)</code> part of the query.</p>
                                    </div>
                                    <div id=add-a-logging-data-source class=scrollspy-content>
                                        <h2 id=add-a-logging-data-source>Add a logging data source</h2>
                                        <p>Grafana supports log data sources, like <a
                                                href=https://grafana.com/oss/loki />Loki</a>. Just like for metrics, you
                                            first need to add your data source to Grafana.</p>
                                        <ol>
                                            <li>In the side bar, hover your cursor over the
                                                <strong>Configuration</strong> (gear) icon, and then click <strong>Data
                                                    Sources</strong>.</li>
                                            <li>Click <strong>Add data source</strong>.</li>
                                            <li>In the list of data sources, click <strong>Loki</strong>.</li>
                                            <li>In the URL box, enter <a href=http://loki:3100>http://loki:3100</a>.
                                            </li>
                                            <li>Click <strong>Save & Test</strong> to save your changes.</li>
                                        </ol>
                                        <p>Loki is now available as a data source in Grafana.</p>
                                    </div>
                                    <div id=explore-your-logs class=scrollspy-content>
                                        <h2 id=explore-your-logs>Explore your logs</h2>
                                        <p>Grafana Explore not only lets you make ad-hoc queries for metrics, but lets
                                            you explore your logs as well.</p>
                                        <ol>
                                            <li>
                                                <p>In the side bar, click the <strong>Explore</strong> (compass) icon.
                                                </p>
                                            </li>
                                            <li>
                                                <p>In the data source list at the top, select the <strong>Loki</strong>
                                                    data source.</p>
                                            </li>
                                            <li>
                                                <p>In the <strong>Query editor</strong>, enter:</p>
                                                <pre><code>{filename=&quot;/var/log/tns-app.log&quot;}
</code></pre>
                                            </li>
                                            <li>
                                                <p>Grafana displays all logs within the log file of the sample
                                                    application. The height of each bar encodes the number of logs that
                                                    were generated at that time.</p>
                                            </li>
                                            <li>
                                                <p>Click and drag across the bars in the graph to filter logs based on
                                                    time.</p>
                                            </li>
                                        </ol>
                                        <p>Not only does Loki let you filter logs based on labels, but on specific
                                            occurrences.</p>
                                        <p>Let&rsquo;s generate an error, and analyze it with Explore.</p>
                                        <ol>
                                            <li>
                                                <p>In the <a href=http://localhost:8081>sample application</a>, post a
                                                    new link without a URL to generate an error in your browser that
                                                    says <code>empty url</code>.</p>
                                            </li>
                                            <li>
                                                <p>Go back to Grafana and enter the following query to filter log lines
                                                    based on a substring:</p>
                                                <pre><code>{filename=&quot;/var/log/tns-app.log&quot;} |= &quot;error&quot;
</code></pre>
                                            </li>
                                            <li>
                                                <p>Click on the log line that says
                                                    <code>level=error msg="empty url"</code> to see more information
                                                    about the error.</p>
                                            </li>
                                        </ol>
                                        <p>Logs are helpful for understanding what went wrong. Later in this tutorial,
                                            you&rsquo;ll see how you can correlate logs with metrics from Prometheus to
                                            better understand the context of the error.</p>
                                    </div>
                                    <div id=build-a-dashboard class=scrollspy-content>
                                        <h2 id=build-a-dashboard>Build a dashboard</h2>
                                        <p>A <em>dashboard</em> gives you an at-a-glance view of your data and lets you
                                            track metrics through different visualizations.</p>
                                        <p>Dashboards consist of <em>panels</em>, each representing a part of the story
                                            you want your dashboard to tell.</p>
                                        <p>Every panel consists of a <em>query</em> and a <em>visualization</em>. The
                                            query defines <em>what</em> data you want to display, whereas the
                                            visualization defines <em>how</em> the data is displayed.</p>
                                        <ol>
                                            <li>
                                                <p>In the side bar, hover your cursor over the <strong>Create</strong>
                                                    (plus sign) icon and then click <strong>Dashboard</strong>.</p>
                                            </li>
                                            <li>
                                                <p>Click <strong>Add new panel</strong>.</p>
                                            </li>
                                            <li>
                                                <p>In the <strong>Query editor</strong> below the graph, enter the query
                                                    from earlier and then press Shift + Enter:</p>
                                                <pre><code>sum(rate(tns_request_duration_seconds_count[5m])) by(route)
</code></pre>
                                            </li>
                                            <li>
                                                <p>In the <strong>Legend</strong> field, enter
                                                    <strong>{{route}}</strong> to rename the time series in the legend.
                                                    The graph legend updates when you click outside the field.</p>
                                            </li>
                                            <li>
                                                <p>In the Panel editor on the right, under <strong>Settings</strong>,
                                                    change the panel title to &ldquo;Traffic&rdquo;.</p>
                                            </li>
                                            <li>
                                                <p>Click <strong>Apply</strong> in the top-right corner to save the
                                                    panel and go back to the dashboard view.</p>
                                            </li>
                                            <li>
                                                <p>Click the <strong>Save dashboard</strong> (disk) icon at the top of
                                                    the dashboard to save your dashboard.</p>
                                            </li>
                                            <li>
                                                <p>Enter a name in the <strong>New name</strong> field and then click
                                                    <strong>Save</strong>.</p>
                                            </li>
                                        </ol>
                                    </div>
                                    <div id=annotate-events class=scrollspy-content>
                                        <h2 id=annotate-events>Annotate events</h2>
                                        <p>When things go bad, it often helps if you understand the context in which the
                                            failure occurred. Time of last deploy, system changes, or database migration
                                            can offer insight into what might have caused an outage. Annotations allow
                                            you to represent such events directly on your graphs.</p>
                                        <p>In the next part of the tutorial, we will simulate some common use cases that
                                            someone would add annotations for.</p>
                                        <ol>
                                            <li>
                                                <p>To manually add an annotation, click anywhere in your graph, then
                                                    click <strong>Add annotation</strong>.</p>
                                            </li>
                                            <li>
                                                <p>In <strong>Description</strong>, enter <strong>Migrated user
                                                        database</strong>.</p>
                                            </li>
                                            <li>
                                                <p>Click <strong>Save</strong>.</p>
                                                <p>Grafana adds your annotation to the graph. Hover your mouse over the
                                                    base of the annotation to read the text.</p>
                                            </li>
                                        </ol>
                                        <p>Grafana also lets you annotate a time interval, with <em>region
                                                annotations</em>.</p>
                                        <p>Add a region annotation:</p>
                                        <ol>
                                            <li>Press Ctrl (or Cmd on macOS), then click and drag across the graph to
                                                select an area.</li>
                                            <li>In <strong>Description</strong>, enter <strong>Performed load
                                                    tests</strong>.</li>
                                            <li>In <strong>Tags</strong>, enter <strong>testing</strong>.</li>
                                        </ol>
                                        <p>Manually annotating your dashboard is fine for those single events. For
                                            regularly occurring events, such as deploying a new release, Grafana
                                            supports querying annotations from one of your data sources. Let&rsquo;s
                                            create an annotation using the Loki data source we added earlier.</p>
                                        <ol>
                                            <li>
                                                <p>At the top of the dashboard, click the <strong>Dashboard
                                                        settings</strong> (gear) icon.</p>
                                            </li>
                                            <li>
                                                <p>Go to <strong>Annotations</strong> and click <strong>Add Annotation
                                                        Query</strong>.</p>
                                            </li>
                                            <li>
                                                <p>In <strong>Name</strong>, enter <strong>Errors</strong>.</p>
                                            </li>
                                            <li>
                                                <p>In <strong>Data source</strong>, select <strong>Loki</strong>.</p>
                                            </li>
                                            <li>
                                                <p>In <strong>Query</strong>, enter the following query:</p>
                                                <pre><code>{filename=&quot;/var/log/tns-app.log&quot;} |= &quot;error&quot;
</code></pre>
                                            </li>
                                        </ol>
                                        <ol>
                                            <li>Click <strong>Add</strong>. Grafana displays the Annotations list, with
                                                your new annotation.</li>
                                            <li>Click the <strong>Go back</strong> arrow to return to your dashboard.
                                            </li>
                                        </ol>
                                        <p>The log lines returned by your query are now displayed as annotations in the
                                            graph.</p>
                                        <p>Being able to combine data from multiple data sources in one graph allows you
                                            to correlate information from both Prometheus and Loki.</p>
                                        <p>Annotations also work very well alongside alerts. In the next and final
                                            section, we will set up an alert for our app <code>grafana.news</code> and
                                            then we will trigger it. This will provide a quick intro to our new Alerting
                                            platform.</p>
                                    </div>
                                    <div id=create-a-grafana-managed-alert class=scrollspy-content>
                                        <h2 id=create-a-grafana-managed-alert>Create a Grafana Managed Alert</h2>
                                        <p>Alerts allow you to identify problems in your system moments after they
                                            occur. By quickly identifying unintended changes in your system, you can
                                            minimize disruptions to your services.</p>
                                        <p>Grafana&rsquo;s new alerting platform debuted with Grafana 8. A year later,
                                            with Grafana 9, it became the default alerting method. In this step we will
                                            create a Grafana Managed Alert. Then we will trigger our new alert and send
                                            a test message to a dummy endpoint.</p>
                                        <p>The most basic alert consists of two parts:</p>
                                        <ol>
                                            <li>A <em>Contact Point</em> - A Contact point defines how Grafana delivers
                                                an alert. When the conditions of an <em>alert rule</em> are met, Grafana
                                                notifies the contact points, or channels, configured for that alert.
                                                Some popular channels include email, webhooks, Slack notifications, and
                                                PagerDuty notifications.</li>
                                            <li>An <em>Alert rule</em> - An Alert rule defines one or more
                                                <em>conditions</em> that Grafana regularly evaluates. When these
                                                evaluations meet the rule&rsquo;s criteria, the alert is triggered.</li>
                                        </ol>
                                        <p>To begin, let&rsquo;s set up a webhook Contact Point. Once we have a usable
                                            endpoint, we&rsquo;ll write an alert rule and trigger a notification.</p>
                                        <h3 id=create-a-contact-point-for-grafana-managed-alerts>Create a Contact Point
                                            for Grafana Managed Alerts</h3>
                                        <p>In this step, we&rsquo;ll set up a new Contact Point. This contact point will
                                            use the <em>webhooks</em> channel. In order to make this work, we also need
                                            an endpoint for our webhook channel to receive the alert. We will use <a
                                                href=https://requestbin.com>requestbin.com</a> to quickly set up that
                                            test endpoint. This way we can make sure that our alert is actually sending
                                            a notification somewhere.</p>
                                        <ol>
                                            <li>Browse to <a href=https://requestbin.com>requestbin.com</a>.</li>
                                            <li>Under the <strong>Create Request Bin</strong> button, click the
                                                <strong>public bin</strong> link.</li>
                                        </ol>
                                        <p>Your request bin is now waiting for the first request.</p>
                                        <ol>
                                            <li>Copy the endpoint URL.</li>
                                        </ol>
                                        <p>Next, let&rsquo;s configure a Contact Point in Grafana&rsquo;s Alerting UI to
                                            send notifications to our Request Bin.</p>
                                        <ol>
                                            <li>Return to Grafana. In Grafana&rsquo;s side bar, hover your cursor over
                                                the <strong>Alerting</strong> (bell) icon and then click <strong>Contact
                                                    points</strong>.</li>
                                            <li>Click <strong>+ New Contact Point</strong>.</li>
                                            <li>In <strong>Name</strong>, write <strong>RequestBin</strong>.</li>
                                            <li>In <strong>Type</strong>, choose <strong>webhook</strong>. It&rsquo;s
                                                the last option in the dropdown.</li>
                                            <li>In <strong>Url</strong>, paste the endpoint to your request bin.</li>
                                            <li>Click <strong>Test</strong> to send a test alert to your request bin.
                                            </li>
                                            <li>Navigate back to the request bin you created earlier. On the left side,
                                                there&rsquo;s now a <code>POST /</code> entry. Click it to see what
                                                information Grafana sent.</li>
                                            <li>Return to Grafana and click <strong>Save contact point</strong>.</li>
                                        </ol>
                                        <p>We have now created a dummy webhook endpoint and created a new Alerting
                                            Contact Point in Grafana. Now we can create an alert rule and link it to
                                            this new channel.</p>
                                        <h3 id=add-an-alert-rule-to-grafana>Add an Alert Rule to Grafana</h3>
                                        <p>Now that Grafana knows how to notify us, it&rsquo;s time to set up an alert
                                            rule:</p>
                                        <ol>
                                            <li>In Grafana&rsquo;s side bar, hover the cursor over the
                                                <strong>Alerting</strong> (bell) icon and then click <strong>Alert
                                                    rules</strong>.</li>
                                            <li>Click <strong>+ New Alert Rule</strong>.</li>
                                            <li>A new page will appear with four distinct sections. Let&rsquo;s review
                                                them one at a time. For <strong>Section 1</strong>, leave
                                                <strong>Grafana Managed Alert</strong> as the chosen alert type. Name
                                                the rule <code>fundamentals-test</code> and for <strong>group</strong>
                                                write <code>fundamentals</code>.</li>
                                            <li>For <strong>Section 2</strong>, find the <strong>query A</strong> box.
                                                Choose your Prometheus datasource and enter the same query that we used
                                                in our earlier panel:
                                                <code>sum(rate(tns_request_duration_seconds_count[5m])) by(route)</code>.
                                                Press <strong>Run query</strong>. You should see some data in the graph.
                                            </li>
                                            <li>Now scroll down to the <strong>query B</strong> box. For
                                                <strong>Operation</strong> choose <code>Classic condition</code>. <a
                                                    href=https://grafana.com/docs/grafana/latest/alerting/unified-alerting/alerting-rules/create-grafana-managed-rule/#single-and-multi-dimensional-rule>You
                                                    can read more about classic and multi-dimensional conditions
                                                    here</a>. For conditions enter the following:
                                                <code>WHEN last() OF A IS ABOVE 0.2</code></li>
                                            <li>In <strong>Section 3</strong>, enter <code>30s</code> for the
                                                <strong>Evaluate every</strong> field. For the purposes of this
                                                tutorial, the evaluation interval is intentionally short. This makes it
                                                easier to test. In the <strong>For</strong> field, enter
                                                <code>0m</code>. This setting makes Grafana wait until an alert has
                                                fired for a given time before Grafana sends the notification.</li>
                                            <li>In <strong>Section 4</strong>, you can add some sample text to your
                                                summary message. <a
                                                    href=https://grafana.com/docs/grafana/latest/alerting/unified-alerting/message-templating />Read
                                                more about message templating here</a>.</li>
                                            <li>Click <strong>Save and Exit</strong> at the top of the page.</li>
                                            <li>Because we only have one contact point (our Request Bin webhook), our
                                                alerts will default to use it. As a system grows, admins can use the
                                                <strong>Notification Policies</strong> setting to organize and match
                                                alert rules to specific contact points.</li>
                                        </ol>
                                        <h3 id=trigger-a-grafana-managed-alert>Trigger a Grafana Managed Alert</h3>
                                        <p>We have now configured an alert rule and a contact point. Now lets see if we
                                            can trigger a Grafana Managed Alert by generating some traffic on our sample
                                            application.</p>
                                        <ol>
                                            <li>Browse to <a href=http://localhost:8081>localhost:8081</a>.</li>
                                            <li>Repeatedly click the vote button or refresh the page to generate a
                                                traffic spike.</li>
                                        </ol>
                                        <p>Once the query
                                            <code>sum(rate(tns_request_duration_seconds_count[5m])) by(route)</code>
                                            returns a value greater than <code>0.2</code> Grafana will trigger our
                                            alert. Browse to the Request Bin we created earlier and find the sent
                                            Grafana alert notification with details and metadata.</p>
                                    </div>
                                    <div id=summary class=scrollspy-content>
                                        <h2 id=summary>Summary</h2>
                                        <p>In this tutorial you learned about fundamental features of Grafana. To do so,
                                            we ran several Docker on your local machine. When you are ready to clean up
                                            this local tutorial environment, run this command:</p>
                                        <pre><code>docker-compose down -v
</code></pre>
                                        <h3 id=learn-more>Learn more</h3>
                                        <p>Check out the links below to continue your learning journey with
                                            Grafana&rsquo;s LGTM stack.</p>
                                        <ul>
                                            <li><a
                                                    href=https://grafana.com/docs/grafana/latest/features/datasources/prometheus />Prometheus</a>
                                            </li>
                                            <li><a
                                                    href=https://grafana.com/docs/grafana/latest/features/datasources/loki />Loki</a>
                                            </li>
                                            <li><a
                                                    href=https://grafana.com/docs/grafana/latest/features/explore />Explore</a>
                                            </li>
                                            <li><a href=https://grafana.com/docs/grafana/latest/alerting />Alerting
                                                Overview</a></li>
                                            <li><a
                                                    href=https://grafana.com/docs/grafana/latest/alerting/create-alerts />Alert
                                                rules</a></li>
                                            <li><a
                                                    href=https://grafana.com/docs/grafana/latest/alerting/notifications />Contact
                                                Points</a></li>
                                        </ul>
                                    </div>
                                    </p>
                                </div>
                            </div>
                        </main>
                    </div>
                </div>
            </div>
        </div>
       
        <div class=page-footer>
            <div class=wrapper>
                <div class="row my-2 justify-content-between">
                    <div class="col--sm-12 col--md-6">
                        <a href= />
                        <img src=/static/assets/internal/grafana_logo-web.svg alt="Grafana Labs Logo" width=225>
                        </a>
                    </div>
                    <div class="col--sm-12 col--md-6 d-flex align-self-center justify-content-flex-end">
                        <div class=page-footer__nav-social>
                            <a href=https://www.facebook.com/grafana/ target=_blank rel=noopener
                                aria-label="Grafana Labs on Facebook"><i class="fa fa-facebook"></i></a>
                            <a href=https://twitter.com/grafana target=_blank rel=noopener
                                arial-label="Grafana Labs on Twitter"><i class="fa fa-twitter"></i></a>
                            <a href=https://www.linkedin.com/company/grafana-labs/ target=_blank rel=noopener
                                aria-label="Grafana Labs on LinkedIn"><i class="fa fa-linkedin"></i></a>
                            <a href=https://github.com/grafana/ target=_blank rel=noopener
                                arial-label="Grafana Labs on GitHub"><i class="fa fa-github"></i></a>
                            <a href=https://www.youtube.com/channel/UCYCwgQAMm9sTJv0rgwQLCxw target=_blank rel=noopener
                                aria-label="Grafana Labs on YouTube"><i class="fa fa-youtube"></i></a>
                        </div>
                    </div>
                </div>
                <hr class=m-0>
         
                <hr>
              
   
            </div>
        </div>
        
    </div>
   
</body>

</html>
