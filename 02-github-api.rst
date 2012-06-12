https://github.com/pypa/
http://developer.github.com/v3/

::
    >>> import requests
    >>> from pprint import pprint as pp
    >>> requests.get('https://api.github.com/orgs/pypa')
    >>> requests.get('https://api.github.com/orgs/pypa').json
    >>> pp(requests.get('https://api.github.com/orgs/pypa').json)
    >>> pp(requests.get('https://api.github.com/orgs/pypa/members').json)
    >>> pp(requests.get('https://api.github.com/orgs/pypa/events').json)

    >>> def get_org_events(user_id):
    ...     url = 'https://api.github.com/orgs/%s/events' % user_id
    ...     return requests.get(url).json

for event in get_org_events('pypa'):
    print event['created_at'], event['type'], event['actor']['login']

::
    >>> for event in get_org_events('pypa'):
    ...     if event['type'] == 'IssueCommentEvent':
    ...         payload = event['payload']
    ...         print payload['comment']['url']
    ...         print '   ', payload['comment']['body'][:50]
    ...         print
    ...     elif event['type'] == 'PushEvent':
    ...         for commit in event['payload']['commits']:
    ...             print commit['url'][:75]
    ...             print '    %s: %s' % (commit['author']['name'],
    ...                                   commit['message'][:30])
