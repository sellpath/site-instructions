import { GITHUB_API_URL, owner, repo } from "@root/constants";

const directoryPath = 'path/to/directory'; // Replace with the directory path
async function getDirectoryContents(
owner: string,
repo: string,
directoryPath: string
) {
const url = `${GITHUB_API_URL}/repos/${owner}/${repo}/contents/${directoryPath}`;
try {
const response = await fetch(url, {
headers: {
Accept: 'application/vnd.github.v3+json',
},
});
if (!response.ok) {
throw new Error(`Failed to fetch directory contents: ${response.status}`);
}
const data = await response.json();
return data; // List of files and directories
} catch (error) {
console.error(error);
return null;
}
}
async function displayDirectoryContents() {

const contents = await getDirectoryContents(owner, repo, directoryPath);
if (contents) {
contents.forEach((item: any) => {
console.log(`${item.type}: ${item.name} - ${item.path}`);
});
}
}
// Call the function to display the directory contents
displayDirectoryContents();
