import requests

def get_github_profile(username):
    url = f'https://api.github.com/users/{username}'
    response = requests.get(url)
    
    if response.status_code == 200:
        data = response.json()
        print(f"GitHub Profile for {username}:\n")
        print(f"Name: {data['name']}")
        print(f"Bio: {data['bio']}")
        print(f"Followers: {data['followers']}")
        print(f"Following: {data['following']}")
        print(f"Public Repositories: {data['public_repos']}")
    else:
        print(f"Failed to retrieve GitHub profile for {username}. Status code: {response.status_code}")

# Replace 'Acrasking' with the desired GitHub username
get_github_profile('Acrasking')
