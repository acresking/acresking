import requests

def get_github_profile(AcrasKing):
    url = f'https://api.github.com/users/AcrasKing'
    response = requests.get(url)
    
    if response.status_code == 200:
        data = response.json()
        print(f"GitHub Profile for {AcrasKing}:\n")
        print(f"Name: {data['AcrasKing']}")
        print(f"Bio: {data['bio']}")
        print(f"Followers: {data['followers']}")
        print(f"Following: {data['following']}")
        print(f"Public Repositories: {data['public_repos']}")
    else:
        print(f"Failed to retrieve GitHub profile for {AcrasKing}. Status code: {response.status_code}")

# Replace 'Acrasking' with the desired GitHub username
get_github_profile('Acrasking')
